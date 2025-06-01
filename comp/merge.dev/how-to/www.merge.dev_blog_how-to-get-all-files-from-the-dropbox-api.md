---
url: "https://www.merge.dev/blog/how-to-get-all-files-from-the-dropbox-api"
title: "How to GET all files from the Dropbox API"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-get-all-files-from-the-dropbox-api#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-get-all-files-from-the-dropbox-api#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-get-all-files-from-the-dropbox-api#)

Table of contents

[Preparation](https://www.merge.dev/blog/how-to-get-all-files-from-the-dropbox-api#preparation)

[Getting files & folders from Dropbox](https://www.merge.dev/blog/how-to-get-all-files-from-the-dropbox-api#getting-files-and-folders-from-dropbox)

[Building a production-level integration](https://www.merge.dev/blog/how-to-get-all-files-from-the-dropbox-api#building-a-production-level-integration)

[Conclusion](https://www.merge.dev/blog/how-to-get-all-files-from-the-dropbox-api#conclusion)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-all-files-from-the-dropbox-api)

##### Just for you

No items found.

# How to GET all files from the Dropbox API

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cae2a8b75b1b6143228_How_to_GET_all_files_from_the_Dropbox_API.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538592637517da99427a_62eff91f58ad1560481786c6_Max.webp)

Max Gong

Platform

@Merge

Dropbox is a cloud-based file storage hosting and sharing platform that offers solutions across enterprise and consumer. They have deep integrations with workplace and collaboration platforms and many larger companies use Dropbox to collaborate and share assets. A common query when it comes to using the Dropbox API is how to GET all files from the Dropbox API and how to handle authentication.

We’ll be using Postman to demonstrate how to get Dropbox files via the API.

## **Preparation**

In order to access Dropbox’s API, you’ll first need a sandbox Dropbox account, as well as an OAuth application to get an access token.

The best way to get both of these is to create a Dropbox developer account.

1\. Sign up for a developer account [here](https://www.dropbox.com/developers). Click **Create apps** to sign up.

2\. Once you’re done signing up, navigate [here](https://www.dropbox.com/developers/apps) and click **Create app.** ‍

3\. Choose “Scoped access” and “Full Dropbox”, so that your app has access to all files & folders.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b7f4aea05fb37348cfe_LNHSQ620CJujj67Th1I6RXOZ-g7VLbaXm2CSZI3Li-x_ti0d0-i39-mAzXuZu4tIgjuG2qQaJFvuTvm_PC61TQIfRtvPj9Wyp_jF7F_AygGHdm-LK61qiNCtQjuzx-_BHQMAZpJWUobO5E0DXJaozms.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b7f4aea05fb37348cfe_LNHSQ620CJujj67Th1I6RXOZ-g7VLbaXm2CSZI3Li-x_ti0d0-i39-mAzXuZu4tIgjuG2qQaJFvuTvm_PC61TQIfRtvPj9Wyp_jF7F_AygGHdm-LK61qiNCtQjuzx-_BHQMAZpJWUobO5E0DXJaozms.webp)

4\. For this article, we’ll just be showing you how to access the API. So instead of implementing the full OAuth flow, we’ll generate a temporary access token. Click **Generate access token** to generate an access token. Save the token, as we’ll be using it to make API calls.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b7fe73573bdb9ff4b08_Xij3PjC5whWvw0Zo6KcDnS77-rremY87O7YRJTFmUZ7kSSid1Dwk0d5gE5LHdStGstKV6eLugLZEIreanEikaV6kbkJytpY0hwn0CAYcPZysM-wQ2tF5xY015hJVV4ke_XiVrtivAWkqfT-XMbKLah4.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b7fe73573bdb9ff4b08_Xij3PjC5whWvw0Zo6KcDnS77-rremY87O7YRJTFmUZ7kSSid1Dwk0d5gE5LHdStGstKV6eLugLZEIreanEikaV6kbkJytpY0hwn0CAYcPZysM-wQ2tF5xY015hJVV4ke_XiVrtivAWkqfT-XMbKLah4.webp)

And now you’ve set up your developer account as well as an OAuth app!

To get a sandbox Dropbox account, simply sign up for a free account [here](https://www.dropbox.com/register).

_Related:_ [_How the most popular file storage APIs work_](https://www.merge.dev/blog/file-storage-api)

## **Getting files & folders from Dropbox**

Create a new collection in Postman. In the **Authorization** section, select **Bearer Token** as the type. Copy and paste your access token into **Token**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b8043f7fc3c91cba321_CW0p-VjFjZ-P-fByoqDjlMXtvRlw3v-zsdRSgFoO1mI4cU0_lOfq7sgJBLXEL-8BGiepHLRbqP_t2Pty4vTzUIwVe8QVy_zb0Fl7ALu84aU7b9qMoWG35Qb0wFYqKmh667tmCPi3cJ06pd2bmaEbiE8.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b8043f7fc3c91cba321_CW0p-VjFjZ-P-fByoqDjlMXtvRlw3v-zsdRSgFoO1mI4cU0_lOfq7sgJBLXEL-8BGiepHLRbqP_t2Pty4vTzUIwVe8QVy_zb0Fl7ALu84aU7b9qMoWG35Qb0wFYqKmh667tmCPi3cJ06pd2bmaEbiE8.webp)

At the highest level, Dropbox is organized by namespaces. To access the namespaces, make the following API call:

```json
POST https://api.dropboxapi.com/2/team/namespaces/list
```

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b80d1c78914b8373875_CNxIJp3I97--wq-LHeYkPvjB07jVY8TkfpTCThPZynVUKerWTcIGo6xsHIKvKwAd54lhkIxgtNLaWH-hhaWhX5XTZgj4easmNVAS0FnBrDBVDJe-ZvYXIq8b1rNfseOS3JBUnpwH3rXP82kyO5vpVKc.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b80d1c78914b8373875_CNxIJp3I97--wq-LHeYkPvjB07jVY8TkfpTCThPZynVUKerWTcIGo6xsHIKvKwAd54lhkIxgtNLaWH-hhaWhX5XTZgj4easmNVAS0FnBrDBVDJe-ZvYXIq8b1rNfseOS3JBUnpwH3rXP82kyO5vpVKc.webp)

Before accessing the files in the namespace, you’ll need a user’s account ID. This is required by Dropbox to impersonate a user to access files and folders. Make an API call to:

```json
POST https://api.dropboxapi.com/2/team/members/list
```

‍

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b7f48941b09a954fe0f_arlDtqwBI8G0mocj1t6tYfn2t-H4PWLEQcHIpaqLSls_wjhQe6RjbaXdjPFwuHy0liPEPC_58LROCog3d0yjjdoKfZQdhs_Bwng1jwFO2AQcSz5xgarm7JzeyiJ1Vpei5r1G2X3qnncEPQwEgDbwSFQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b7f48941b09a954fe0f_arlDtqwBI8G0mocj1t6tYfn2t-H4PWLEQcHIpaqLSls_wjhQe6RjbaXdjPFwuHy0liPEPC_58LROCog3d0yjjdoKfZQdhs_Bwng1jwFO2AQcSz5xgarm7JzeyiJ1Vpei5r1G2X3qnncEPQwEgDbwSFQ.webp)

To access all files and folders within the namespace, including nested folders and files, you’ll need the following.

Make an API call to:

```json
POST https://api.dropboxapi.com/2/files/list_folder
```

Include `Dropbox-API-path_Root` in the header, with the following header value:

```json
{".tag": "root", "root": "[INSERT NAMESPACE ID]"}
```

Include `Dropbox-API-Select-Admin` in the header, with header value equal to any of the admin `team_member_id` from the previous step.

Add the path of the namespace in the path, add 2 parameters:

`path` to indicate which folder or namespace to pull from. Here, use the namespace id, and prepend it with `ns:`.

`recursive` to indicate whether to get nested files and folders, not just the immediate files & folders under the namespace. Here, set to **_true_**.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b802f73e66107491ff8__PTERTe4SXpuyn8IJtuWXO20djCEalVX-MAY0IDznpgyJOVwimsrOvj3-g5KYXh-bmci5ijhH_vBaz4aXbzoX2rfNnmR8HSZPJl-st93VBoy6sFw5C5RC2IjX-hOgM3MXl6uTxrM9gNsVoZDqgDvVrs.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b802f73e66107491ff8__PTERTe4SXpuyn8IJtuWXO20djCEalVX-MAY0IDznpgyJOVwimsrOvj3-g5KYXh-bmci5ijhH_vBaz4aXbzoX2rfNnmR8HSZPJl-st93VBoy6sFw5C5RC2IjX-hOgM3MXl6uTxrM9gNsVoZDqgDvVrs.webp)

The initial API call will most likely not return all files and folders. You’ll have to use cursor-based pagination, and you’ll make a call to:

```json
POST https://api.dropboxapi.com/2/files/list_folder/continue
```

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b7f9921040e20a8259d__p018wAEIAHIr5PlNsRGTNZ9F0BELL6NAsn3NuWRcNtjzin-X-Dyk5DhAy_Jo9BG5-kN85KSCtCirn6WawggOiOgYmKqqBRcMUWFkhNrydPwACYbAz45NJeUedX0CMkTWXXS6GaVCRG1yDs2k0-ejVc.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64108b7f9921040e20a8259d__p018wAEIAHIr5PlNsRGTNZ9F0BELL6NAsn3NuWRcNtjzin-X-Dyk5DhAy_Jo9BG5-kN85KSCtCirn6WawggOiOgYmKqqBRcMUWFkhNrydPwACYbAz45NJeUedX0CMkTWXXS6GaVCRG1yDs2k0-ejVc.webp)

That wraps up how to get all files and folders in your Dropbox account via API!

_Related:_ [_A guide to retrieving folders from the Dropbox API via Python_](https://www.merge.dev/blog/dropbox-api-get-folders)

## **Building a production-level integration**

There are a few factors to consider when turning this simple POC into a production-level integration:

- You’ll need to implement cursor-based pagination. Dropbox uses a separate endpoint `https://api.dropboxapi.com/2/files/list_folder/continue` with a provided cursor to output the rest of the response. This is especially important so that you don’t miss any data.
- If you need to do periodic syncs, you’ll also need to implement periodic polling of the Dropbox APIs. You’ll also have to implement rate-limit handling to make sure you don’t exceed Dropbox’s rate limits.
- You’ll need to implement logic to handle the Dropbox OAuth flow, including providing a redirect URI and a bit of front-end support. You’ll be unable to use the expiring access token for production purposes.

## **Conclusion**

This article showed you how to GET all files from Dropbox.

As your integration needs grow, [Merge](https://www.merge.dev/) connects your product to hundreds of integrations with one single API in HR, recruiting, accounting, ticketing, CRM, and marketing automation.

If your organization needs to not only GET files from [Dropbox](https://merge.dev/integrations/dropbox), but also [SharePoint](https://merge.dev/integrations/sharepoint), [Box](https://merge.dev/integrations/box), [Google Drive](https://merge.dev/integrations/google-drive), and others, check out the Merge [File Storage Unified API](https://merge.dev/categories/file-storage-api)! As with all of Merge’s Unified APIs, one API connection is enough to offer your users integrations to all File Storage platforms.

Learn more about Merge by [scheduling a demo with one of our integration experts](https://merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-get-all-files-from-the-dropbox-api).

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Max Gong

Platform

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

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=92faf4f1-497f-43a6-968c-c07ddfc2e413&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=248e1b99-63c6-40df-aeae-79210b98c5f7&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-all-files-from-the-dropbox-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=92faf4f1-497f-43a6-968c-c07ddfc2e413&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=248e1b99-63c6-40df-aeae-79210b98c5f7&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-all-files-from-the-dropbox-api&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=f6288658-9917-405d-90ef-e30771f7f9f7&bo=2&sid=32f4f1503e8d11f0a9e5df94eb321694&vid=32f4dc403e8d11f0a46d4d0625024d60&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20GET%20all%20files%20from%20the%20Dropbox%20API&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-get-all-files-from-the-dropbox-api&r=&lt=616&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=787651)