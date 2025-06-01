---
url: "https://www.merge.dev/blog/merge-and-chatgpt"
title: "Unblock sales in under 30 minutes with Merge + ChatGPT"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/merge-and-chatgpt#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/merge-and-chatgpt#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/merge-and-chatgpt#)

Table of contents

[Background before getting started‍](https://www.merge.dev/blog/merge-and-chatgpt#background-before-getting-started)

[Implement Merge Linking Flow Into Your Frontend and Backend‍](https://www.merge.dev/blog/merge-and-chatgpt#implement-merge-linking-flow-into-your-frontend-and-backend)

[What’s Next?](https://www.merge.dev/blog/merge-and-chatgpt#whats-next)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmerge-and-chatgpt)

##### Just for you

No items found.

# Unblock sales in under 30 minutes with Merge + ChatGPT

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7725b20320c1dad429_Merge_%252525252B_ChatGPT.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Henry Baer

@Merge

You can use our platform for any number of reasons.

Maybe you’re releasing an AI-driven product or feature and you _need_ the data provided by integrations to power its capabilities; or you’re looking for ways to improve the customer experience and you’ve pinpointed integrations as the solution; or you see integrations as essential to differentiating your product in the market and acquiring new customers.

Whatever your reasons, you see integrations as a critical part of your product strategy and you’ve landed on Merge to help execute it.

The question then becomes how you implement Merge.

While we’ve already made the implementation process fast and easy through [our SDKs](https://docs.merge.dev/sdk/) and our LLM-powered tool, [Blueprint](https://merge.dev/blog/meet-blueprint-our-new-ai-powered-tool-to-build-better-integrations), you can accelerate your backend integration with Merge even further by leveraging [ChatGPT](https://openai.com/blog/chatgpt).

We’ll walk you through the process, step-by-step, so that you can get Merge up and running in a matter of minutes.

## Background before getting started  ‍

We’ll implement Merge with a single ChatGPT prompt. All you need is to input two variables in the prompt:

- {X} — To indicate your frontend framework
- {Y} — To indicate your backend service


In addition, you’ll need access to the following tools:

‍

1\. A Merge Account: [sign-up here for free\\
\\
‍](https://app.merge.dev/signup?_gl=1*4h1m9e*_gcl_au*MTU3MDg3NDc2Ny4xNjkwOTAxOTk1*_ga*OTcxNTU2NDQxLjE2OTA5MDE5OTY.*_ga_S6X9VBDBJN*MTY5MDkwMTk5NS4xLjAuMTY5MDkwMTk5NS42MC4wLjA.) 2\. Access to ChatGPT: [sign-up here](https://auth0.openai.com/u/signup/identifier?state=hKFo2SBlLVBlRldSeVJXaGJwNjNrdVFKMFY5NkpNd3Z3a0tUMaFur3VuaXZlcnNhbC1sb2dpbqN0aWTZIEwtTy01NFNOR3hCM0JSSFp1MjVRZms3dnY2YzlvVloxo2NpZNkgVGRKSWNiZTE2V29USHROOTVueXl3aDVFNHlPbzZJdEc)

## Implement Merge Linking Flow Into Your Frontend and Backend  ‍

Merge authorizes your users' integrations through a prebuilt, comprehensive onboarding tool called [Merge Link](https://docs.merge.dev/get-started/link/). This requires Merge Link to be configured in your front end.

This modal will interact with your back end, and your back end will interact via API call with Merge to verify and authenticate an integration.

To generate code that implements Merge Linking into your app, use the following prompt (remember to fill out the variables at the end—{X} to indicate your frontend framework and {Y} to indicate your backend service):

````python
You will be asked to implement Merge Link. Use the following code snippets to help you:

(The following is a Django Rest Framework and React implementation of Merge Link.) views.py: ``` from rest_framework.decorators import api_view from rest_framework.response import Response import requests @api_view(['POST']) def create_link_token(request): body = { "end_user_origin_id": request.data.get('organization_id'), "end_user_organization_name": request.data.get('organization_name'), "end_user_email_address": request.data.get('email_address'), "categories": request.data.get('categories', []) } headers = {"Authorization": f"Bearer {request.data.get('api_key')}"} link_token_url = "https://api.merge.dev/api/integrations/create-link-token" link_token_result = requests.post(link_token_url, data=body, headers=headers) link_token = link_token_result.json().get("link_token") return Response({"link_token": link_token}) @api_view(['GET']) def retrieve_account_token(request, public_token): headers = {"Authorization": f"Bearer {request.headers.get('api_key')}"} account_token_url = "https://api.merge.dev/api/integrations/account-token/{}".format(public_token) account_token_result = requests.get(account_token_url, headers=headers) account_token = account_token_result.json().get("account_token") return Response({"account_token": account_token}) ``` urls.py: ``` from django.urls import path from .views import create_link_token, retrieve_account_token urlpatterns = [ path('create-link-token/', create_link_token, name='create-link-token'), path('retrieve-account-token/<str:public_token>/', retrieve_account_token, name='retrieve-account-token'), ] ``` app.js ``` import React, { useState, useCallback } from "react"; import axios from 'axios'; import { useMergeLink } from "@mergeapi/react-merge-link"; const App = () => { const [linkToken, setLinkToken] = useState(null); const onSuccess = useCallback((public_token) => { // Call backend to retrieve account token axios.get(`http://localhost:8000/merge-app/retrieve-account-token/${public_token}/`, { headers: { 'api_key': 'YOUR_API_KEY' }}) .then(res => { console.log('Account Token: ', res.data.account_token); }) .catch(err => { console.error(err); }) }, []); const { open, isReady } = useMergeLink({ linkToken, onSuccess, }); // Generate link token when component mounts React.useEffect(() => { const body = { organization_id: 'ORG_ID', organization_name: 'ORG_NAME', email_address: 'EMAIL_ADDRESS', categories: ['hris', 'ats', 'accounting', 'ticketing', 'crm'], api_key: 'YOUR_API_KEY' }; axios.post('http://localhost:8000/merge-app/create-link-token/', body) .then(res => { setLinkToken(res.data.link_token); }) .catch(err => { console.error(err); }) }, []); return ( <button disabled={!isReady} onClick={open}> Preview linking experience </button> ); }; export default App; ``` The FE can also be implemented in Vue, with: ``` <template> <section> <merge-link :linkToken="ADD_GENERATED_LINK_TOKEN" v-bind="{ onSuccess }" /* :tenantConfig="{ apiBaseURL: 'https://api-eu.merge.dev' OR your specified single tenant API base URL }" */> <template slot="button" slot-scope="props"> <!-- Replace with your preferred view --> <button @click="props.onClick">Open Merge Link</button> </template> </merge-link> </section> </template> <script> import MergeLink from "@mergeapi/vue-merge-link"; export default { components: { MergeLink }, methods: { onSuccess(token) { // Pass token to your backend (Step 3) }, }, }; </script> ``` The FE can be done in vanilla JS/HTML with: ``` <button id="open-link-button">Start linking</button> <script src="https://cdn.merge.dev/initialize.js"></script> <script type="text/javascript"> const button = document.getElementById("open-link-button"); button.disabled = true; function onSuccess(public_token) { // Send public_token to server (Step 3) } MergeLink.initialize({ // Replace ADD_GENERATED_LINK_TOKEN with the token retrieved from your backend (Step 1) linkToken: "ADD_GENERATED_LINK_TOKEN", onSuccess: (public_token) => onSuccess(public_token), onReady: () => (button.disabled = false), // A value of `true` for `shouldSendTokenOnSuccessfulLink` makes Link call `onSuccess` // immediately after an account has been successfully linked instead of after the user // closes the Link modal. shouldSendTokenOnSuccessfulLink: true, // tenantConfig: { // apiBaseURL: "https://api-eu.merge.dev" /* OR your specified single tenant API base URL */ // }, }); button.addEventListener("click", function () { MergeLink.openLink(); })</script> ```

Make a full implementation of Merge Link with an {X} backend and {Y} Frontend
````

## What’s Next?

Now that you can authorize production-quality, customer-facing integrations, the next step is to build the business logic that fits your use case.

To help you, we’ve built out a library of resources in our Documentation, including access to [SDKs](https://docs.merge.dev/sdk/), [Guides](https://docs.merge.dev/guides/), and a [Get Started](https://docs.merge.dev/get-started/introduction/) onboarding center.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Henry Baer

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=41a7e84b-a64f-48c9-b905-6d2376fa1691&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b009e7eb-4b4f-4e5a-981a-9f6bf85c7c21&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmerge-and-chatgpt&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=41a7e84b-a64f-48c9-b905-6d2376fa1691&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=b009e7eb-4b4f-4e5a-981a-9f6bf85c7c21&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmerge-and-chatgpt&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=ad0ac2f4-f592-4385-908b-a1c8ac403f58&bo=2&sid=25a7b1303e8c11f0a70c5b4a3a1e3cc7&vid=25a876303e8c11f0ba64556233eaf5ff&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Unblock%20sales%20in%20under%2030%20minutes%20with%20Merge%20%2B%20ChatGPT&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmerge-and-chatgpt&r=&lt=933&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=572809)