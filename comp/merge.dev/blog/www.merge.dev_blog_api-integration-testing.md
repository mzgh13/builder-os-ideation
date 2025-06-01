---
url: "https://www.merge.dev/blog/api-integration-testing"
title: "How to run API integration tests"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-integration-testing#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-integration-testing#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-integration-testing#)

Table of contents

[What is API integration testing?](https://www.merge.dev/blog/api-integration-testing#what-is-api-integration-testing)

[What does API integration testing solve?](https://www.merge.dev/blog/api-integration-testing#what-does-api-integration-testing-solve)

[API integration testing versus unit testing](https://www.merge.dev/blog/api-integration-testing#api-integration-testing-versus-unit-testing)

[Key steps in API integration testing](https://www.merge.dev/blog/api-integration-testing#key-steps-in-api-integration-testing)

[Best practices for testing API integrations](https://www.merge.dev/blog/api-integration-testing#best-practices-for-testing-api-integrations)

[Example of API integration testing](https://www.merge.dev/blog/api-integration-testing#example-of-api-integration-testing)

[Final thoughts](https://www.merge.dev/blog/api-integration-testing#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-testing)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735c33a545135e134b_RAG_challenges.webp)**API integration security: what it is and best practices**](https://www.merge.dev/blog/api-integration-security)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d8578f0b3a81cb7b7c635a_Blog%20Header%20Brand%20Refresh%20(2).png)**13 API integration tools to consider using in 2025**](https://www.merge.dev/blog/api-integration-tools)

# How to run API integration tests

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74f43703047123799f_Anthropic_API_key.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Manish Hatwalne

@Merge

As with any software system, you need to test how APIs interact with each other and within your system to ensure they’re exchanging data correctly and reliably—which is where API integration testing comes into play.

In this tutorial, you'll learn what API integration testing is, why it's important, how to perform it (using an example), and some best practices to keep in mind when doing so.

## What is API integration testing?

API integration testing is the process of testing your integration through making sure that every component of the integration will work as intended with the API. There are many components to integration testing, including the API authentication, pagination, rate limiting, and response bodies.

_Related:_ [_A guide to API integration tools_](https://www.merge.dev/blog/api-integration-tools)

## What does API integration testing solve?

API integration testing is a crucial part of the development process, and prevents a lot of heavy-duty bandaid work down the road.

Here's some benefits fromAPI integration testing:

- **Ensure reliability, data accuracy, and stability:** Testing ensures that your integrations are reliable and can handle the expected load (i.e offers stability). It also verifies the accuracy of the data that’s being exchanged between systems.

- **Improve error handling:** [API integrations](https://www.merge.dev/blog/api-integration) can be complex and prone to errors. Testing not only helps identify and fix these errors but also improves the error handling within the code that deals with error responses from the APIs.

- **Check performance:** Testing allows you to detect performance bottlenecks and optimize the integrations while also considering relevant API rate limits.

- **Maintain compatibility:** APIs and systems can change over time. Testing ensures that updates in one system remain compatible with all the other systems involved, which maintains seamless communication.

- **Improve security:** Thorough testing can help identify security vulnerabilities, ensuring that data exchanges between systems remain safe and protected.

#### Avoid testing integrations at scale with Merge

Merge lets you add hundreds of integrations to your product through Unified API.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-testing)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## API integration testing versus unit testing

Unit testing is where the smallest piece of code, or unit, is tested individually. Integration testing is conducted separately and combines the modules of unit testing into a single test to confirm the functionality of an entire integration.

At Merge, we add unit tests for every backend change, and we layer on integration tests for every integration we build. Whenever we make a change to the integration, it may not require us to make unit test modifications, but it absolutely will require integration test modifications.

## Key steps in API integration testing

Here are recommended steps for API integration testing:

1. Come up with testing plan for your integrations
2. Build varied cases and use cases to test
3. Run tests on the integration
4. Track, report, and resolve any errors that come up from those tests
5. Retest the integration
6. Repeat this process until the integration no longer runs into bugs

## Best practices for testing API integrations

Here are some general best practices that can help you develop an effective API integration testing plan:

### Choose a network request mocking library when possible

You should try to use specialized network request mocking libraries (such as requests\_mock) for API integration tests. These libraries simulate real network interactions more accurately. They also provide the ability to isolate testing scenarios, reduce dependency on external APIs, simulate error conditions for comprehensive testing (as demonstrated in the TestAPIIntegrations class), and improve testing speed by eliminating actual network requests. Additionally, these libraries enhance the reliability and efficiency of API integration tests, especially for tests that involve numerous network requests.

### Evaluate error handling implementations

You should cover various error scenarios during API interactions to ensure that your system can handle them without crashing. For example, in the API integration tests earlier, the requests\_mock code simulated an error response from the API: `mock.get("", status_code=500)`

This part tested whether the get\_product\_availability(...) code correctly handles API errors without crashing. Depending on your specific implementation, you can simulate various HTTP errors (such as HTTP 404 or HTTP 401) to verify if the corresponding code appropriately handles them.

### Focus on boundary values

Test extreme input values to identify unexpected behaviors and ensure that your system can gracefully handle these inputs. For instance, you can test the get\_converted\_price(...) function by providing extremely low or high values for product prices. This verifies if the code appropriately handles such values, including displaying helpful error messages for invalid inputs.

### Test for backward compatibility

Conduct tests to verify that modifications to the third-party APIs don't disrupt existing functionality.

For instance, imagine you have an application that relies on the Google Maps API for location data. When Google Maps makes changes to its APIs, you need to modify your API integration code and the associated tests to mock the modified API responses and parameters, as required. You also have to perform backward compatibility testing to make sure that the rest of your system remains functional with the latest API changes. If something breaks with those changes, you need to fix that as well. This prevents any disruptions for existing users.

### Use realistic data

Create tests using real-world data scenarios. This guarantees that your system can adeptly manage real user interactions.

For instance, when simulating user profile responses from an authentication API, use realistic names that contain Unicode characters to validate your system's ability to manage these names in both code and databases.

Another example is to use an accurate USD-INR conversion rate, such as 82.6, instead of simplified 82 (an integer) to ensure that the corresponding code can handle decimal values correctly.

### Keep tests updated

Keep your tests up-to-date with evolving APIs so that they remain reliable indicators of your system's functionality. As your codebase evolves, new features, improvements, or bug fixes may alter the behavior of your system. Failing to update tests can lead to false positives or negatives, where tests pass even though the system isn't functioning as intended or tests fail due to changes you intentionally made.

_Related:_ [_A guide to integrating REST APIs_](https://www.merge.dev/blog/rest-api-integration)

## Example of API integration testing

The following Python code demonstrates the integration of two public APIs. The first API handles currency price conversion, and the second API provides information for a given zip code in the U.S.

To understand the process of integrating these APIs and conducting integration tests, follow these steps:

### Install the required libraries

You can create a new [virtual environment](https://docs.python.org/3/library/venv.html) and activate it before installing the Python libraries mentioned later. This allows you to isolate your project and avoid any dependency conflicts.

This code requires that you install the libraries requests and requests\_mock, and you can install them using a pip like the following: `pip install requests requests_mock`

### Integrate external APIs

After you've installed the required libraries, you need to create a new file named api\_integration.py and paste the following code into it:

```python

import requests

def get_converted_price(product_price: int, conversion_currency: str) -> float:
    converted_price = None
    base_currency = "usd"
    api_url = f"https://cdn.jsdelivr.net/gh/fawazahmed0/currency-api@1/latest/currencies/{base_currency}/{conversion_currency.lower()}.json"

    try:
        resp = requests.get(api_url)
        if resp.ok:     # HTTP OK
            currency_data = resp.json()
            converted_price = product_price * currency_data[conversion_currency]
            print(f"Converted price for the product: {round(converted_price, 2)} {conversion_currency.upper()}")
        else:
            print(f"Response: {resp.text} (HTTP-{resp.status_code})")
    except Exception as ex:
        print(f"Error: {ex}")    # show error
    finally:
        return converted_price

def get_product_availability(zipcode: int) -> bool:
    availability = None
    skip_states = ["Idaho", "Indiana", "Kansas", "Kentucky", "Mississippi", "Nebraska", "North Carolina",\
                   "Oklahoma", "South Carolina", "South Dakota", "Tennessee", "Texas", "Utah", "Virginia", "Wyoming"]
    api_url = f"https://api.zippopotam.us/us/{zipcode}"

    try:
        resp = requests.get(api_url)
        if resp.ok:     # HTTP OK
            zip_data = resp.json()
            state = zip_data["places"][0]["state"]
            availability = False if state in skip_states else True
            print(f"The product is available in: {state} - {availability}")
        else:
            print(f"Response: {resp.text} (HTTP-{resp.status_code})")
    except Exception as ex:
        print(f"Error: {ex}")    # show error
    finally:
        return availability

```

The first function, get\_converted\_price(...), integrates the [currency conversion API](https://github.com/fawazahmed0/currency-api#readme). This function requires two parameters: product\_price and conversion\_currency. The former denotes the price in the base currency (USD), while the latter indicates the local currency to which the product price should be converted.

The code obtains the most recent USD conversion rate for the specified currency via the currency conversion API using this call: requests.get(api\_url). This conversion rate is then used to compute the relevant product price, which is returned by the function. For instance, similar converted prices are often displayed when purchasing domains.

The second function, get\_product\_availability(...), integrates the [zip code information API](https://api.zippopotam.us/). This function takes a single parameter: zipcode of the location to determine product availability (limited to US zip codes). Additionally, this function maintains a list of states where the product is not available: skip\_states.

Similar to the previous function, the code retrieves location data via the zip code information API. It extracts the state associated with the given zip code from this data. If this extracted state is among those listed in skip\_states, the function returns False; otherwise, it returns True.

Both these functions handle unexpected errors using a try-except-finally block. Moreover, they print their computed results before returning them, making it easier to examine the output while testing these API integrations.

_Related:_ [_What is API integration management? Here's what you need to know_](https://www.merge.dev/blog/api-integration-management)

### Test the API integrations

API integration testing utilizes the [requests-mock](https://pypi.org/project/requests-mock/) library, specifically designed for mocking HTTP requests. It allows you to mock different HTTP methods and responses without actually sending the requests to the real server. In addition, the built-in Python module unittest provides a standard testing framework.

The class TestAPIIntegrations is subsequently displayed and includes five tests for the previously-discussed functions (i.e. get\_converted\_price(...) and get\_product\_availability(...)). You can copy and paste this code into a new file: api\_integration\_tests.py:

```python

import unittest
import requests_mock
from api_integration import get_converted_price, get_product_availability

class TestAPIIntegrations(unittest.TestCase):

    def test_get_converted_price(self):
        test_data = {"date": "2023-09-01", "inr": 82.6}
        expected_price = 8260
        with requests_mock.Mocker() as mock:
            mock.get("https://cdn.jsdelivr.net/gh/fawazahmed0/currency-api@1/latest/currencies/usd/inr.json", json=test_data)
            calculated_price = get_converted_price(100, "inr")
            self.assertEqual(calculated_price, expected_price, f"Price calculation is incorrect.")

    def test_get_converted_price_failure(self):
        with requests_mock.Mocker() as mock:
            mock.get("https://cdn.jsdelivr.net/gh/fawazahmed0/currency-api@1/latest/currencies/usd/inr.json", status_code=404)
            calculated_price = get_converted_price(100, "inr")
            self.assertIsNone(calculated_price, "Price is _not_ None.")

    def test_get_product_availability_true(self):
        test_data = {"post code": "90210", "places": [{"place name": "Beverly Hills", "state": "California"}]}
        with requests_mock.Mocker() as mock:
            mock.get("https://api.zippopotam.us/us/90210", json=test_data)
            product_availability = get_product_availability(90210)
            self.assertTrue(product_availability, f"Product availability is incorrect.")

    def test_get_product_availability_false(self):
        test_data = {"post code": "75001", "places": [{"place name": "Addison", "state": "Texas"}]}
        with requests_mock.Mocker() as mock:
            mock.get("https://api.zippopotam.us/us/75001", json=test_data)
            product_availability = get_product_availability(75001)
            self.assertFalse(product_availability, f"Product availability is incorrect.")

    def test_get_product_availability_failure(self):
        with requests_mock.Mocker() as mock:
            mock.get("https://api.zippopotam.us/us/75001", status_code=500)
            product_availability = get_product_availability(75001)
            self.assertIsNone(product_availability, f"Product availability is incorrect.")

if __name__ == '__main__':
    unittest.main(verbosity=2)

```

Now, examine this code for test\_get\_converted\_price(). Here, the requests\_mock library is used within the context of the with statement to temporarily replace the behavior of the requests.get(...) method. The mock is set up to respond with specific JSON data (test\_data) whenever a GET request is directed at the corresponding API.

When the get\_converted\_price(...) function is called during the test, it interacts with the mock instead of making an actual network request. Consequently, the function calculates the price using the conversion rate provided by this test data:

{"date": "2023-09-01", "inr": 82.6}

In the end, the expected price, which is 8,260 (100 ✕ 82.6), is compared to the calculated price returned by the get\_converted\_price(...) function using the mock API response: `self.assertEqual(calculated_price, expected_price, f"Price calculation is incorrect.")`

The corresponding message is displayed only if the assertion fails.

Utilizing requests\_mock in the test allows you to verify that the code within the function get\_converted\_price(...) behaves as expected using test\_data that simulates the API response.

Now, consider the code for test\_get\_converted\_price\_failure(). This test emulates an API failure by simulating an HTTP-404 response, as shown in this code snippet: `mock.get("", status_code=404)`

This test verifies that the get\_converted\_price(...) function correctly returns None: `self.assertIsNone(calculated_price, "Price is _not_ None.")`

Similarly, these subsequent tests validate the functionality of the get\_product\_availability(...) function:

- **`test_get_product_availability_true()`** checks whether the function correctly returns True for the given zip code where the product is available. It simulates this API response:

```python

{"post code": "90210", "places": [{"place name": "Beverly Hills", "state": "California"}]}

```

- **`test_get_product_availability_false()`** ensures that the function properly returns False for the provided zip code where the product is not available. It emulates this API response:

````python

```json
{"post code": "75001", "places": [{"place name": "Addison", "state": "Texas"}]}
```

````

- **`test_get_product_availability_failure()`** verifies that the function correctly returns None when an API failure occurs. In this scenario, it simulates an HTTP-500 response:

```python

mock.get("", status_code=500)

```

These tests cover a few possible scenarios. More tests can be added to test specific scenarios (such as extreme product prices or non-U.S. zip codes) as required.

It's crucial to understand that any change in the API response format, for whatever reason, requires modifications not just in the original code but also in the mock responses of such tests.

_Related:_ [_Examples of API integrations_](https://www.merge.dev/blog/api-integration-examples)

### Run API integration tests

The following code snippet runs all the tests discussed previously: `if __name__ == '__main__':    unittest.main(verbosity=2)`

The parameter verbosity=2 ensures that these tests generate detailed output when they are executed, as shown here:

```python

$ python api_integration_tests.py
test_get_converted_price (__main__.TestAPIIntegrations) ... Converted price for the product: 8260.0 INR
ok
test_get_converted_price_failure (__main__.TestAPIIntegrations) ... Response:  (HTTP-404)
ok
test_get_product_availability_failure (__main__.TestAPIIntegrations) ... Response:  (HTTP-500)
ok
test_get_product_availability_false (__main__.TestAPIIntegrations) ... The product is available in: Texas - False
ok
test_get_product_availability_true (__main__.TestAPIIntegrations) ... The product is available in: California - True
ok

----------------------------------------------------------------------
Ran 5 tests in 0.324s

OK

```

This test output also includes print(...) statements from the functions get\_converted\_price(...) and get\_product\_availability(...), showing their results and error-handling.

The complete code for this tutorial is available in this [GitHub repository](https://github.com/manishh/gifts-giveaways/tree/master/python/merge-api-integration-testing).

## Final thoughts

As you can tell from our examples, testing API integrations in-house can be labor-intensive—especially when there are several integrations that need to be tested over time.

If your team is looking to [implement product integrations](https://www.merge.dev/blog/product-integrations) and doesn’t want to handle all of the tedious, time-consuming tasks that come with building and maintaining them—like testing—, you can leverage Merge.

Merge offers a unified API that lets you connect to hundreds of applications automatically, from CRM solutions to file storage tools to HRIS platforms.

To learn more about Merge and to discover how it can help transform your product integration strategy, you can [schedule a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-integration-testing).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Manish Hatwalne

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=46034bbf-9872-459d-bdd5-d92f6d692c48&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1ab54764-d170-4364-ad9b-d616b9497cb3&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-testing&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=46034bbf-9872-459d-bdd5-d92f6d692c48&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=1ab54764-d170-4364-ad9b-d616b9497cb3&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-testing&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

td.doubleclick.net

# This site can’t be reached

The webpage at **https://td.doubleclick.net/td/rul/331218389?random=1748743949051&cv=11&fst=1748743949051&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200zb833796111&gcd=13l3l3l3l1l1&dma=0&tag\_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351866~103351868~104481633~104481635~104559073~104559075~104612245~104612247&ptag\_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351866~103351868~104481633~104481635~104559073~104559075~104612245~104612247&u\_w=1280&u\_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-testing&\_ng=1&hn=www.googleadservices.com&frm=0&tiba=How%20to%20run%20API%20integration%20tests&npa=0&pscdl=noapi&auid=1292905906.1748743949&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86\_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config** might be temporarily down or it may have moved permanently to a new web address.

ERR\_SOCKET\_NOT\_CONNECTED

The webpage at **https://td.doubleclick.net/td/rul/331218389?random=1748743949051&cv=11&fst=1748743949051&fmt=3&bg=ffffff&guid=ON&async=1&gtm=45be55s2v9181790984za200zb833796111&gcd=13l3l3l3l1l1&dma=0&tag\_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351866~103351868~104481633~104481635~104559073~104559075~104612245~104612247&ptag\_exp=101509157~103116026~103200004~103233427~103252644~103252646~103351866~103351868~104481633~104481635~104559073~104559075~104612245~104612247&u\_w=1280&u\_h=1024&url=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-testing&\_ng=1&hn=www.googleadservices.com&frm=0&tiba=How%20to%20run%20API%20integration%20tests&npa=0&pscdl=noapi&auid=1292905906.1748743949&uaa=x86&uab=64&uafvl=Google%2520Chrome%3B137.0.7151.55%7CChromium%3B137.0.7151.55%7CNot%252FA)Brand%3B24.0.0.0&uamb=0&uam=&uap=Linux%20x86\_64&uapv=6.6.72&uaw=0&fledge=1&data=event%3Dgtag.config** might be temporarily down or it may have moved permanently to a new web address.

![](<Base64-Image-Removed>)![](<Base64-Image-Removed>)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=8a4ff38f-cd62-433c-8346-eebb4be1943a&bo=2&sid=de62df403e8d11f0a2b9d39f6672e705&vid=de6366503e8d11f0a2f025eff0666d46&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20run%20API%20integration%20tests&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-integration-testing&r=&lt=326&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=608112)