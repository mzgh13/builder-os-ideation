---
url: "https://www.merge.dev/blog/create-invoices-quickbooks-online-api-php"
title: "How to create invoices from the QuickBooks Online API in PHP with OAuth2"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/create-invoices-quickbooks-online-api-php#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/create-invoices-quickbooks-online-api-php#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/create-invoices-quickbooks-online-api-php#)

Table of contents

[How to Create Invoices with the QuickBooks API in PHP](https://www.merge.dev/blog/create-invoices-quickbooks-online-api-php#how-to-create-invoices-with-the-quickbooks-api-in-php)

[Creating and Fetching Invoices Using a Unified API Solution](https://www.merge.dev/blog/create-invoices-quickbooks-online-api-php#creating-and-fetching-invoices-using-a-unified-api-solution)

[Accounting Integration Resources and more](https://www.merge.dev/blog/create-invoices-quickbooks-online-api-php#accounting-integration-resources-and-more)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcreate-invoices-quickbooks-online-api-php)

##### Just for you

No items found.

# How to create invoices from the QuickBooks Online API in PHP with OAuth2

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856ceba5ba95f529a7f7f2_How_to_Create_Invoices_from_the_QuickBooks_API_in_PHP_with_OAuth2.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Amr Abdou

@Merge

[QuickBooks](https://quickbooks.intuit.com/) is one of the most well-known [accounting software solutions](https://merge.dev/blog/accounting-concepts-the-developers-essential-guide). Its ease of use, quick learning curve, affordable pricing, and simple interface has made it the solution of choice for over 3.4 million businesses worldwide, from independent contractors to growing enterprises. As a developer, you might have to integrate QuickBooks with other internal company software like [project management](https://merge.dev/categories/ticketing-api) or [CRM solutions](https://merge.dev/categories/crm-api). The huge customer base of QuickBooks also offers great potential for countless SaaS integrations with other cloud-based business tools.

In this article, you'll learn how to create invoices using the QuickBooks API in PHP. The tutorial covers how to create a QuickBooks app, connect your software to QuickBooks, handle authentication using Oauth2.0, and create and fetch invoice information programmatically using the QuickBooks API. As a compliment to this specific, tactical, tutorial, you might find [our strategic ebook on Accounting API integrations helpful](https://merge.dev/learning/guide-to-accounting-api-integrations?0ce679a4_page=1).

You can find the code for this tutorial at this [GitHub repository](https://github.com/AmrAbdou/QuickbooksInvoicesTutorialPHP/tree/main).

## **How to Create Invoices with the QuickBooks API in PHP**

To follow along with this tutorial and the code examples, you need [PHP 5.6](https://www.php.net/manual/en/install.php) or higher, [Composer](https://getcomposer.org/download/), and [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) client installed on your local machine.

### **Create an Intuit Developer Account**

To connect your app to the QuickBooks API, you need to [create an Intuit Developer account](https://developer.intuit.com/app/developer/homepage). Intuit is the company that created QuickBooks, and the developer platform is named after the parent company.

### **Create an App**

Next, create an app on the Intuit Developer platform. This step is essential to generate the get that you'll use to connect to the OAuth 2.0 server, generate access tokens, and make API calls.

OAuth 2.0 is the authorization standard used to integrate your app with QuickBooks. Only registered apps can connect to the Intuit OAuth2.0 server, call the API, and integrate with a company QuickBooks account.

To create your app, log in to your developer account, click the Dashboard item in the navigation menu, then click **Create an App**. After you fill out the short form with your app info, you'll be directed to the dashboard of your newly created app.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e87039d6cdbcd73f6b1b87_6421f7eb50af7f2264d317cb_image1.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e87039d6cdbcd73f6b1b87_6421f7eb50af7f2264d317cb_image1.webp)

### **Get Client Keys and Define Redirect URI**

You now need to copy the client keys that you'll use to perform API requests. From the dashboard of your app, click **Keys & credentials** under **Development Settings**. These credentials are for your testing environment. When you publish your app, you'll need to replace those credentials with the ones under the **Production Settings** menu.

You'll also need to create at least one redirect uniform resource identifier (URI). These URIs handle responses from the OAuth 2.0 server and are called after the user authorizes the connection. For the scope of this article, you'll need one URI.

In this project, you'll use `http://localhost:3000/callback.php` as the callback URI. Create a URI with this address as shown in the image below:

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e87039d6cdbcd73f6b1b7f_6421ffcd7ca3b83d03d6ae27_image3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e87039d6cdbcd73f6b1b7f_6421ffcd7ca3b83d03d6ae27_image3.webp)

_Related:_ [_QuickBooks Online integration examples_](https://www.merge.dev/blog/quickbooks-api)

### **Project Structure**

For this tutorial, you'll be creating a demo app to log in and connect a sandbox company using OAuth2.0, create invoices, and fetch created invoices for this sandbox company.

This sample project includes creating six PHP files:

- **index.php:** This is a homepage file that includes basic HTML and PHP code to display the access token data.
- **connectCompany:** This is used to log in and connect a sandbox company using OAuth2.0 and to generate and save the access token.
- **callback.php:** This is where the login request to the server is directed; it is the callback URI that you already set in the app settings.
- **createInvoice.php:** This contains the function that includes the invoice creation logic.
- **getInvoices.php:** This contains a function to fetch invoices.
- **config.php:** This is a file to store the environment variables you'll need to connect to the API.

### **Install QuickBooks PHP SDK**

QuickBooks offers an official PHP SDK for the Online Accounting API. To install the QuickBooks Online PHP SDK via composer, run the following line in your terminal after navigating to your project folder:

```php
composer require quickbooks/v3-php-sdk
```

### **Create a Config File**

This **config.php** file will contain the environment variables that you'll use to connect to the QuickBooks servers. You'll use these variables later in every file for all the API requests' authentication.

After you create the **config.php** file, paste this code into it:

```php
<?php
return array(
    'authorizationRequestUrl' => 'https://appcenter.intuit.com/connect/oauth2',
    'tokenEndPointUrl' => 'https://oauth.platform.intuit.com/oauth2/v1/tokens/bearer',
    'client_id' => YOUR CLIENT ID HERE',
    'client_secret' => YOUR CLIENT SECRET HERE,
    'oauth_scope' => 'com.intuit.quickbooks.accounting',
    'oauth_redirect_uri' => 'http://localhost:3000/callback.php',
)
?>

```

The environment variables included in this code are as follows:

- **authorizationRequestUrl:** This is the Intuit server OAuth2.0 URL.
- **'tokenEndPointUrl':** This is the token endpoint on Intuit servers.
- **client\_id:** Replace this with the Client ID key from your app settings.
- **client\_secret:** Replace this with the Client Secret key from your app settings.
- **oauth\_scope:** QuickBooks apps have two scopes: accounting and payments. Since the scope of this code is to handle creating and fetching invoices, the code uses the accounting scope.
- **oauth\_redirect\_uri:** This is the URI that you defined earlier in your app settings. It's where all the API responses will be handled.

#### Integrate with every ERP solution via Merge

Learn how Merge's Unified API lets you integrate your product with more than a dozen ERP solutions in a matter of days.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcreate-invoices-quickbooks-online-api-php)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

### **Create an Index File**

The index file is a homepage file with minimal HTML to help test your code.

Start by creating a file named **index.php**, then add this PHP code at the top:

```php

<?php
require_once(__DIR__ . '/vendor/autoload.php');
use QuickBooksOnline\API\DataService\DataService;
$config = include('config.php');

session_start();

// Configure Data Service
$dataService = DataService::Configure(array(
    'auth_mode' => 'oauth2',
    'ClientID' => $config['client_id'],
    'ClientSecret' =>  $config['client_secret'],
    'RedirectURI' => $config['oauth_redirect_uri'],
    'scope' => $config['oauth_scope'],
    'baseUrl' => "development"
));

//set the access token using the auth object
if (isset($_SESSION['sessionAccessToken'])) {

    $accessToken = $_SESSION['sessionAccessToken'];
    $accessTokenArray = array('token_type' => 'bearer',
        'access_token' => $accessToken->getAccessToken(),
        'refresh_token' => $accessToken->getRefreshToken(),
        'x_refresh_token_expires_in' => $accessToken->getRefreshTokenExpiresAt(),
        'expires_in' => $accessToken->getAccessTokenExpiresAt()
    );
}
?>
```

The first three lines in this file are to load composer packages, the **config.php** file, and the DataService class from the QuickBooks API. You'll use this class in every step of this tutorial to connect with the API, handle authentication, generate and refresh the access token, and many other functions.

To create an SDK instance using the data service object, you need to provide the right parameter to the `DataService::Configure()` function. You have set this up already in the **config.php** file, so the parameters used are all imported from the `$config` array.

The following code inside the if statement checks if a token has already been generated and saved in the session variables. If a token is generated, the token information is stored in `$accessTokenArray`. This array shows you the most important data that you need from the access token, which will be shown at the bottom of the HTML code below.

Next, add this HTML code:

```html
<!DOCTYPE html>
<html>
<head>

</head>
<body>
    <p><a href="connectCompany.php">OAuth 2.0 Login</a></p>
    <p><a href="createInvoice.php">Create Invoice</a></p>
    <p><a href="getInvoice.php">Fetch Invoices</a></p>

    <p><strong>Access Token:</strong></p>
    <code>
        <?php
        $displayString = isset($accessTokenArray) ? $accessTokenArray : "No Access Token Generated Yet";
        echo json_encode($displayString);
        ?>
    </code>
</body>
```

This code includes three anchor links to handle the OAuth login, create invoices, and fetch invoices, followed by a code block to display the access token data when generated.

### **Log In and Connect Your Sandbox Company**

Every developer account comes with a sandbox company. The invoices that you're going to create and fetch will belong to this company. Before creating invoices, you need to connect this company to your app using OAuth2.0 and get an access token.

To handle the OAuth2.0 login, create a file named **connectCompany.php** and add this code to it:

```php
<?php

require_once(__DIR__ . '/vendor/autoload.php');
use QuickBooksOnline\API\DataService\DataService;

$config = include('config.php');

session_start();

$dataService = DataService::Configure(array(
    'auth_mode' => 'oauth2',
    'ClientID' => $config['client_id'],
    'ClientSecret' =>  $config['client_secret'],
    'RedirectURI' => $config['oauth_redirect_uri'],
    'scope' => $config['oauth_scope'],
    'baseUrl' => "development"
));

$OAuth2LoginHelper = $dataService->getOAuth2LoginHelper();
$authUrl = $OAuth2LoginHelper->getAuthorizationCodeURL();

// Redirect to the Authorization Page
header('location:'.$authUrl);
?>
```

As for the previous file, it starts by loading composer and the config file and creating the SDK instance using the `DataService` class.

OAuth2LoginHelper lets you connect to the OAuth2.0 server, which will allow you to generate the access token. Calling `$OAuth2LoginHelper->getAuthorizationCodeURL()` generates the OAuth2.0 server authorization URL that the last line in this file redirects you to.

After being redirected to the authorization link, you will find a login page where you can log in to your developer account, then confirm connecting the sandbox company. After doing that successfully, you will be redirected to the callback URI. The URI will be something like this:

```html
http://localhost:3000/callback.php?code=AB11670712517C76sWZ7hD3uYh9pLZtlJ1Wk65o0918hz6cxty&state=JZPYH&realmId=4620816365259814850
```

Notice that the URI `http://localhost:3000/callback.php` is the same as the callback URI you previously created in the app settings and also set in the **config.php** file. The two extra variables in the link— `code` and `realmId`—are sent by the OAuth2.0 server for you to use to generate the access token in the next step.

### **Create the Callback Function**

Since the callback URI is `locahost:3000/callback.php`, create a file called **callback.php** to handle the response from the QuickBooks API and generate the access token.

Add the following code to this file:

```php
<?php

require_once(__DIR__ . '/vendor/autoload.php');
use QuickBooksOnline\API\DataService\DataService;

$config = include('config.php');

session_start();

function processCallbackCode()
{

    // Create SDK instance
    $config = include('config.php');
    $dataService = DataService::Configure(array(
        'auth_mode' => 'oauth2',
        'ClientID' => $config['client_id'],
        'ClientSecret' =>  $config['client_secret'],
        'RedirectURI' => $config['oauth_redirect_uri'],
        'scope' => $config['oauth_scope'],
        'baseUrl' => "development"
    ));

    $OAuth2LoginHelper = $dataService->getOAuth2LoginHelper();

    /*
     * Update the OAuth2Token
    */
    $accessToken = $OAuth2LoginHelper->exchangeAuthorizationCodeForToken($_GET['code'], $_GET['realmId']);
    $dataService->updateOAuth2Token($accessToken);

    /*
     * Setting the accessToken for session variable
     */
    $_SESSION['sessionAccessToken'] = $accessToken;
}

processCallbackCode();
header('location:http://localhost:3000');

?>
```

In the `processCallbackCode()` function, the first thing is to create the data service instance and then to load the `OAuth2LoginHelper` object. To generate the access token, this object uses the `exchangeAuthorizationCodeForToken()` method, which takes two arguments—the URI code and `realmId` sent in the callback URI from the previous step.

The final step in this file is calling the `processCallbackCode()` and redirecting to the **index.php** page. If this step was done correctly, you'll find your access token object displayed in the code block that you created in the index page. This is why the code to check for the access token was created in the index file.

### **Create an Invoice**

By now, you should be able to connect and authorize your sandbox company to use your app. Next, it's time to create a file named **createInvoice.php** to handle invoice creation.

In addition to loading the composer packages and importing the `DataService` class, import two facade classes—Customer and Invoice—using the following code:

```php
<?php

require_once(__DIR__ . '/vendor/autoload.php');
use QuickBooksOnline\API\DataService\DataService;
//Import Facade classes you are going to use here
use QuickBooksOnline\API\Facades\Customer;
use QuickBooksOnline\API\Facades\Invoice;

session_start();
```

Then, add the `createInvoice()` function:

```php
function createInvoice()
{
    // Create SDK instance
     $config = include('config.php');
     $dataService = DataService::Configure(array(
        'auth_mode' => 'oauth2',
        'ClientID' => $config['client_id'],
        'ClientSecret' =>  $config['client_secret'],
        'RedirectURI' => $config['oauth_redirect_uri'],
        'scope' => $config['oauth_scope'],
        'baseUrl' => "development"
    ));

    /*
     * Retrieve the accessToken value from session variable
     */
    $accessToken = $_SESSION['sessionAccessToken'];

    /*
     * Update the OAuth2Token of the dataService object
     */
    $dataService->updateOAuth2Token($accessToken);

    /*
     * 1. Create a Customer
     */
    $customerName = 'John-Doe';
    $customerArray = $dataService->Query("select * from Customer where DisplayName='" . $customerName . "'");
    $error = $dataService->getLastError();
    if ($error) {
        var_dump($error);
    } else {
        if (is_array($customerArray) && sizeof($customerArray) > 0) {
            // Assign Customer Object & Print ID
            $customerRef =  current($customerArray);
            echo "Found Customer with Id={$customerRef->Id}.\n\n";
        } else {
            // Create Customer
            $customerRequestObj = Customer::create([\
                "DisplayName" => $customerName\
            ]);
            $customerResponseObj = $dataService->Add($customerRequestObj);
            $error = $dataService->getLastError();
            if ($error) {
                logError($error);
            } else {
                echo "Created Customer with Id={$customerResponseObj->Id}.\n\n";
                $customerRef = $customerResponseObj;
            }
        }
    }

    /*
     * 2. Create an Invoice using the CustomerRef
     */
    $invoiceObj = Invoice::create([\
        "Line" => [\
            "Amount" => 1.00,\
            "DetailType" => "SalesItemLineDetail",\
            "SalesItemLineDetail" => [\
                "Qty" => 2,\
                "ItemRef" => [\
                  "value" => 1,\
                  "name" => "My Service"\
              ]\
          ]\
      ],\
      "CustomerRef"=> [\
        "value"=> $customerRef->Id\
    ]\
]);
    $resultingInvoiceObj = $dataService->Add($invoiceObj);
    $invoiceId = $resultingInvoiceObj->Id;
    echo "Created invoice Id={$invoiceId}";
    $result = json_encode($resultingInvoiceObj, JSON_PRETTY_PRINT);
    print_r($result . "\n\n\n");
}

createInvoice();
```

The function starts by creating the SDK instance, retrieving the access token from the session variables, and updating the token in the same way you did previously.

After the SDK instance creation, `$dataService->Query()` is used to query the customers table and find whether a customer with the selected name exists. If it's found, the returned object is assigned to `$customerRef` so that it can be used for invoice creation. If no customer was found with this name, then `Customer::create()` is used to create the customer object, and `$dataService->Add()` is used to add a customer with this name to your sandbox company. This function returns the customer object if it's been created successfully or an error if otherwise.

The next step is to create the invoice using the `Invoice::create() ` function and then to use `dataService->Add()` to add it. In `Invoice::create()`, two arrays are given. The first is the `Line` array, which includes the invoice information. The second is the customer reference, which uses the customer ID returned from the customer creation.

To create an invoice, you need at least one line item and a customer reference. For more details about the invoice object, check out [Intuit's documentation about it](https://developer.intuit.com/app/developer/qbo/docs/api/accounting/all-entities/invoice).

The final code is to print the created invoice ID and the full response in JSON format using the `json_encode()` function.

### **Fetch Invoice Data**

The last file to create in this project is **getInvoices.php**. In this file, you need to import the invoice facade class along with composer and the DataService class as follows:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');
use QuickBooksOnline\API\DataService\DataService;
use QuickBooksOnline\API\Facades\Invoice;
```

‍

Then, add the `getInvoice()` function:

```php
session_start();

function getInvoice()
{
      // Create SDK instance
   $config = include('config.php');
   $dataService = DataService::Configure(array(
     'auth_mode' => 'oauth2',
     'ClientID' => $config['client_id'],
     'ClientSecret' =>  $config['client_secret'],
     'RedirectURI' => $config['oauth_redirect_uri'],
     'scope' => $config['oauth_scope'],
     'baseUrl' => "development"
  ));

       /*
        * Retrieve the accessToken value from session variable
        */
       $accessToken = $_SESSION['sessionAccessToken'];

       /*
        * Update the OAuth2Token of the dataService object
        */
       $dataService->updateOAuth2Token($accessToken);

       $invoicesArray = $dataService->Query("select * from invoice");

       $error = $dataService->getLastError();
       if ($error) {
        var_dump($error);
     } else {
        if (is_array($invoicesArray) && sizeof($invoicesArray) > 0) {
         $result = json_encode($invoicesArray, JSON_PRETTY_PRINT);
         print_r($result . "\n\n\n");
      }
   }

}
```

In this function, the `$dataService->Query()` method is used to fetch all invoices. It's a powerful function that lets you run SQL queries to read data such as invoices, customers, items, and other accounting records from the user's company.

Here's an example of how to use it to query all invoices sent to a specific customer by customer ID:

```php
$dataService->Query("select * from invoice where Id='" . $customerName . "'");
```

The final code is to check if the invoice query returned any results by checking the length of the array, then to use the `json_encode()` function to use it and print it to your page.

Finally, call the function at the end of the file:

```php
getInvoice();
```

### **Test Your Code**

Congratulations! You're done creating all the functions necessary to log in and authorize a sandbox company, create an invoice, and fetch all invoices or a specific one.

To test your code, start the PHP server from your terminal window at port 3000 and use this command:

```php
php -S localhost:3000
```

After you run the PHP local server, open your browser and navigate to [localhost:3000](http://localhost:3000/). It will display the **index.php** page. Now you can see the homepage that you created in the **index.php** file.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e87038d6cdbcd73f6b1b78_6421f8135fbe926e7a50f38a_image2.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e87038d6cdbcd73f6b1b78_6421f8135fbe926e7a50f38a_image2.webp)

Start by clicking the **Connect Company** link to log in to your developer account and connect your sandbox company. You will then be redirected to the **index.php** page and see the generated access token at the bottom of the page.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e87039d6cdbcd73f6b1b82_6421ffdf7ca3b801cdd6caac_image4.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66e87039d6cdbcd73f6b1b82_6421ffdf7ca3b801cdd6caac_image4.webp)

After generating the token, you can try creating an invoice by clicking **Create Invoice**. The result will appear as a JSON object in the **createInvoice.php** page. You can then test fetching all the invoices by clicking the **Fetch Invoices** link. The result will also appear as a JSON object.

## **Creating and Fetching Invoices Using a Unified API Solution**

As you can see from the small project in this article, developing, testing, and maintaining an integration with the QuickBooks API can be time-consuming. An alternative is to use a unified API solution like [Merge](https://merge.dev/).

A unified API can be defined as an abstraction layer that provides connection to many APIs in one place. Its single data model that integrates with multiple platforms can help you save development time and expand your application to integrate with many other online accounting solutions.

For example, Merge has a single [invoice object](https://docs.merge.dev/accounting/invoices/) that works as a unified object for your API request to any accounting platform that you're integrating your application with.

## **Accounting Integration Resources and more**

In this tutorial, you learned how to create and fetch invoices using the QuickBooks API and OAuth2.0 login in PHP. You also learned how a [unified API accounting solution](https://merge.dev/blog/why-you-need-a-unified-accounting-api) can help you expand your application with less time and effort. All the code for this tutorial is in this [GitHub repository](https://github.com/AmrAbdou/QuickbooksInvoicesTutorialPHP/tree/main). As you continue your work with accounting integrations, you’ll find [our ebook on Accounting API integrations helpful](https://merge.dev/learning/guide-to-accounting-api-integrations?0ce679a4_page=1).

[Merge](https://merge.dev/) is a unified API solution that provides a single programming interface to sync data from multiple third-party platforms, including [Quickbooks](https://merge.dev/integrations/quickbooks-online), [Netsuite](https://merge.dev/integrations/netsuite), and [Xero](https://merge.dev/integrations/xero). It integrates with hundreds of HR, recruiting, and accounting platforms to help you reduce integration and debugging time and focus on building your core product.

_Learn more about Merge by_ [_scheduling a demo with one of our integration experts_](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fcreate-invoices-quickbooks-online-api-php) _._

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Amr Abdou

@Merge

## Read more

[Software scalability: design, strategies and best practices](https://www.merge.dev/blog/software-scalability)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d8578f0b3a81cb7b7c635a_Blog%20Header%20Brand%20Refresh%20(2).png)

### Software scalability: design, strategies and best practices

Insights

[How to integrate with the SharePoint API via Python](https://www.merge.dev/blog/sharepoint-api-python)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f5b2d1e5322f98bcf08952_Blog%20Header%20Brand%20Refresh%20(1).jpg)

### How to integrate with the SharePoint API via Python

Engineering

[How to build integrations for AI agents](https://www.merge.dev/blog/ai-agent-integrations)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d9ca5e423a87d4859f5726_AI%20product%20strategy.png)

### How to build integrations for AI agents

AI

## Subscribe to the Merge Blog

Get stories from Merge straight to your inbox

[Subscribe](https://www.merge.dev/get-in-touch?utm_btn=dr-page-root)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67a0696c88fcb6b1a1d8ad6f_CTA%20Background%20Logo.svg)

### Get our best content every week

Our weekly newsletter provides the best practices you need to build high performing product integrations.

Your email

Thank you! Your submission has been received!

Oops! Something went wrong while submitting the form.

But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_

But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_

But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_

But Merge isn’t just a Unified  API product. Merge is an integration platform to also manage customer integrations. _gradient text_

Qualified

## Looking to add integrations to your product?

Simply and securely add 100s of customer-facing integrations with one API

Get a demoChat with an expertDownload product integrations eBook

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c8d5963f-cffa-4544-a7df-3cac42437c04&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=4fc52d53-faa7-4fb5-926e-d8405edb6f42&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcreate-invoices-quickbooks-online-api-php&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=c8d5963f-cffa-4544-a7df-3cac42437c04&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=4fc52d53-faa7-4fb5-926e-d8405edb6f42&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcreate-invoices-quickbooks-online-api-php&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=1f5f3ad3-2b41-446c-b169-215379532d62&bo=2&sid=41ee60403e8e11f08fd5511c5f3744de&vid=41ee8df03e8e11f08ef5fd09f91eef9a&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20create%20invoices%20from%20the%20QuickBooks%20Online%20API%20in%20PHP%20with%20OAuth2&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fcreate-invoices-quickbooks-online-api-php&r=&lt=523&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=767229)