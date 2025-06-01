---
url: "https://www.merge.dev/blog/merge-sftp"
title: "How Merge SFTP enables your customers to easily sync file-based reports with your product"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/merge-sftp#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/merge-sftp#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/merge-sftp#)

Table of contents

[How Merge SFTP works](https://www.merge.dev/blog/merge-sftp#how-merge-sftp-works)

[Examples of using Merge SFTP](https://www.merge.dev/blog/merge-sftp#examples-of-using-merge-sftp)

[Access Merge SFTP and manual file uploads with ease](https://www.merge.dev/blog/merge-sftp#access-merge-sftp-and-manual-file-uploads-with-ease)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmerge-sftp)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**How to use SDKs to build and maintain API integrations**](https://www.merge.dev/blog/sdk-integration)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**Merge now supports customers and end-users in APAC even further by offering a multi-tenant in Singapore**](https://www.merge.dev/blog/apac-multi-tenant)

# How Merge SFTP enables your customers to easily sync file-based reports with your product

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

APIs offer the most secure, reliable, and robust method of connectivity between applications.

However, APIs aren’t always an option.

A software vendor may not offer APIs or support the endpoints you need; a vendor may force you to enter into a cost-prohibitive partnership agreement to access their APIs; your security team may be relatively unfamiliar with API-based integrations and hasn't approved of their use—and the list goes on.

With these situations in mind, we’ve decided to roll out Merge SFTP.

Using Merge SFTP, your customers can automatically export reports from a system on a regular cadence (e.g., once a day) and add them to a Merge-hosted SFTP server securely. The data in the reports are then normalized into our Common Models and can be fetched and added to your product.

You can read on to learn how, exactly, Merge SFTP can help your customers [sync data via files](https://www.merge.dev/blog/flat-file-integration) automatically or manually.

## **How Merge SFTP works**

The process of using Merge SFTP—which is now available on HiBob, Workday, SAP Success Factors, and ADP—largely mirrors that of our API integrations.

When a customer accesses [Merge Link](https://docs.merge.dev/get-started/link/) in your product, they’ll be prompted to enter their SFTP information for a specific report in an application (e.g., a Statement of Work report in Workday). As part of this flow, the customer will also define the schedule at which the report gets exported and sent to our SFTP server.

[![Where you can enter in your SFTP information in Merge Link](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893d27dde52c9ee32aea_AD_4nXewdMgZVryOl7PiyKGEmizcYC1-6ur0QhkSr1BUqGReokA7Xz7TAN7QVF7sBSMvAVA5mUfeerOeTr5RtOD7yDnQ4fYtzOcorFl_4Sfu3-0df-UkSgCktXAxZrGlS3aKNKMzmW7X2prgAD02MGFMNeReXSH3.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893d27dde52c9ee32aea_AD_4nXewdMgZVryOl7PiyKGEmizcYC1-6ur0QhkSr1BUqGReokA7Xz7TAN7QVF7sBSMvAVA5mUfeerOeTr5RtOD7yDnQ4fYtzOcorFl_4Sfu3-0df-UkSgCktXAxZrGlS3aKNKMzmW7X2prgAD02MGFMNeReXSH3.webp)

Alternatively, your customers can manually upload CSV files via Merge Link.

This process is more labor-intensive to complete, but it lets you get started immediately.

[![How to manually upload CSV files through Merge Link](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893c6e2cf10ff92afa6c_AD_4nXeWcAmeU9Ckv66gUitJ_f9XCoOytikxfbEuGIm6WxtTiKYyJe5bK5ALVqJYjGzXB5VQfl8k3vPl4FmZxWRFhPTYoEY1wsA0lMQYfAdTAJdwtm9uvLjFz3tgtUAk1-eXVaL6AdNPGzyndo0QHF1jERoHb7c9.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893c6e2cf10ff92afa6c_AD_4nXeWcAmeU9Ckv66gUitJ_f9XCoOytikxfbEuGIm6WxtTiKYyJe5bK5ALVqJYjGzXB5VQfl8k3vPl4FmZxWRFhPTYoEY1wsA0lMQYfAdTAJdwtm9uvLjFz3tgtUAk1-eXVaL6AdNPGzyndo0QHF1jERoHb7c9.webp)

For either Merge SFTP or manual uploads, you can also leverage our [Field Mapping feature](https://docs.merge.dev/supplemental-data/field-mappings/overview/) to sync additional types of data from a report to our Common Models.

[![How Merge's Field Mapping feature works](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893dfab31dd3aab015e6_AD_4nXdeKASBekFH72cLclqW-VuvDewUWjgupI8YTVeCmFhiHtg_I8s04VR6_m7hW6ZPhBXl4H9r9GiNxiKtX8ewWe9N8l3PuSdjz26OFYhU1nqx2M7r9l7wi2VT_tDejgZzFdl4qiHiiwotw_bSu-w0zOi-EMQ.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893dfab31dd3aab015e6_AD_4nXdeKASBekFH72cLclqW-VuvDewUWjgupI8YTVeCmFhiHtg_I8s04VR6_m7hW6ZPhBXl4H9r9GiNxiKtX8ewWe9N8l3PuSdjz26OFYhU1nqx2M7r9l7wi2VT_tDejgZzFdl4qiHiiwotw_bSu-w0zOi-EMQ.webp)

_Related:_ [_3 newly-launched Field Mapping features that let you sync custom data more easily_](https://www.merge.dev/blog/field-mapping-features)

## **Examples of using Merge SFTP**

Here are just a few ways Merge SFTP can support your customers’ HRIS and ATS integration needs:

### **Automated user provisioning**

A customer can send a report from their HRIS every day with all of their employees, including those that've joined in the last 24 hours—along with their associated information (e.g., job title).

Then, based on the logic a customer implements in your product, your platform can add the new hires as users and assign them the right set of permissions, automatically.

[![Automated provisioning example using SFTP](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893ce8eb80e17e5fe1a9_AD_4nXcMXfXFkgvOCcgM8aJucl786XzEj8wCDO3OSrDpVpuNpD3FnwjsbWQj1RaTu_NCvH_OzcmYp7wd5sqqeFAf6ztfCH0f7kTHAzKcv66IpzbXgtTH9u6t4oVMwXrPmrKxBObTVB5C0Z11BEx3PE3W8tEfAhf7.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893ce8eb80e17e5fe1a9_AD_4nXcMXfXFkgvOCcgM8aJucl786XzEj8wCDO3OSrDpVpuNpD3FnwjsbWQj1RaTu_NCvH_OzcmYp7wd5sqqeFAf6ztfCH0f7kTHAzKcv66IpzbXgtTH9u6t4oVMwXrPmrKxBObTVB5C0Z11BEx3PE3W8tEfAhf7.webp)

### **Automated user deprovisioning**

A customer can send a daily report of all the employees from their HRIS, including those that have been marked as inactive. Your product can then mark the associated employees as inactive automatically to prevent them from accessing sensitive data and taking unwanted actions.

[![Deprovisioning use case via SFTP](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893c7740ce49924cc7fb_AD_4nXdnitk590LCGXxaAJawpX6YLiQDXXkoymBW2OodogAdPQbUOIEK4T-aztpux68ZPHgafwV8VqodJ13KAlcwr7krBbhpRdia-rBZomSRPIf2LYfQ3SketjEBsRB6BdW6C2mtC8XshludQKOb-X6GAshNq6M.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893c7740ce49924cc7fb_AD_4nXdnitk590LCGXxaAJawpX6YLiQDXXkoymBW2OodogAdPQbUOIEK4T-aztpux68ZPHgafwV8VqodJ13KAlcwr7krBbhpRdia-rBZomSRPIf2LYfQ3SketjEBsRB6BdW6C2mtC8XshludQKOb-X6GAshNq6M.webp)

_Related:_ [_A guide to automated provisioning_](https://www.merge.dev/blog/automated-provisioning)

### **Analyze employee compensation effectively**

Say you offer a solution that lets HR teams analyze employee compensation so that they can make informed comp adjustments over time.

To ensure your product uses accurate, up-to-date compensation data, you can help customers add employee compensation reports from their HRISs on a monthly basis.

Through that report, any comp changes for an employee can be reflected in your product automatically, which includes the in-product dashboards the customer uses.

[![Employee compensation sync use case through SFTP](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893e2ca0422a23218ca1_AD_4nXdm5__E1MuAPTNM6j4ztddoHLU1nQyN-yPWp4ZyWOeTpwbF-jjD_XgjhEQzI23xZTG2wBGTpXEM9klwm_ByRArXByLmYv4Va-nJGw-_X1_ml3In-q6gmTJYuEgk4bGn7fgHfmLZLMHJ-F8Cgt_uUbzOyZJ-.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893e2ca0422a23218ca1_AD_4nXdm5__E1MuAPTNM6j4ztddoHLU1nQyN-yPWp4ZyWOeTpwbF-jjD_XgjhEQzI23xZTG2wBGTpXEM9klwm_ByRArXByLmYv4Va-nJGw-_X1_ml3In-q6gmTJYuEgk4bGn7fgHfmLZLMHJ-F8Cgt_uUbzOyZJ-.webp)

### **Onboard new hires onto your HR software quickly**

Imagine you provide an HRIS solution and want to help customers add new hires to your platform so that they can kickstart the onboarding process easily and quickly.

To help facilitate this, you can enable any customer to send daily reports from their ATS with all of their candidates, including those who’ve been marked as hired within the last 24 hours. These newly-hired candidates can then auto-populate in the customer's instance of your HRIS.

[![Adding employees to HRIS via SFTP](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893d48ba02b9b7ee2116_AD_4nXdnBnaVK4DfLKbdFdVSERHNt55kxQakqF6DXBqWp35pYo6CGX9kUEAAJW7TVLNodi-byrBkEbe0BQ7HmQuGFPSV8R6RJXSxYEAONlUot98uGGdrFsPbUUB7Z1EoJGacThWWyjd_NeB2HCv6oLgKRi_TQrPe.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d0893d48ba02b9b7ee2116_AD_4nXdnBnaVK4DfLKbdFdVSERHNt55kxQakqF6DXBqWp35pYo6CGX9kUEAAJW7TVLNodi-byrBkEbe0BQ7HmQuGFPSV8R6RJXSxYEAONlUot98uGGdrFsPbUUB7Z1EoJGacThWWyjd_NeB2HCv6oLgKRi_TQrPe.webp)

## **Access Merge SFTP and manual file uploads with ease**

Whether you’re on our Professional or Enterprise plan, you can leverage Merge SFTP and manual file uploads at no additional cost.

Simply connect with your dedicated customer success manager to activate the feature. They can also walk you through its setup and provide prompt support should any bugs come up.

Finally, we’re constantly adding new HRIS and ATS integrations to Merge SFTP, so if we don’t support the integrations you want today, we likely will soon.

#### New to Merge?

Learn more about Merge SFTP, our unified API, and our integration observability features by scheduling a demo with one of our integration experts.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmerge-sftp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)

Jon Gitlin

Senior Content Marketing Manager

@Merge

Jon Gitlin is the Managing Editor of Merge's blog. He has several years of experience in the integration and automation space; before Merge, he worked at Workato, an integration platform as a service (iPaaS) solution, where he also managed the company's blog. In his free time he loves to watch soccer matches, go on long runs in parks, and explore local restaurants.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d3254441-d4bc-4840-8061-337c17fab8d3&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b125bfde-35af-4a0a-b599-5355bf034264&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmerge-sftp&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=d3254441-d4bc-4840-8061-337c17fab8d3&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b125bfde-35af-4a0a-b599-5355bf034264&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmerge-sftp&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=199bf414-c607-4e87-a32a-f43146e2b489&bo=2&sid=d51af3503e8d11f09e54dfd495baa27a&vid=d51afc803e8d11f0a5c1f5b27cca9087&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20Merge%20SFTP%20enables%20your%20customers%20to%20easily%20sync%20file-based%20reports%20with%20your%20product&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmerge-sftp&r=&lt=340&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=20515)