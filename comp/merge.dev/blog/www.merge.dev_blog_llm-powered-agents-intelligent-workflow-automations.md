---
url: "https://www.merge.dev/blog/llm-powered-agents-intelligent-workflow-automations"
title: "How to use LLM-powered agents to build intelligent workflow automations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/llm-powered-agents-intelligent-workflow-automations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/llm-powered-agents-intelligent-workflow-automations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/llm-powered-agents-intelligent-workflow-automations#)

Table of contents

[Address customer feedback effectively](https://www.merge.dev/blog/llm-powered-agents-intelligent-workflow-automations#address-customer-feedback-effectively)

[Analyze employee sentiment and provide actionable takeaways](https://www.merge.dev/blog/llm-powered-agents-intelligent-workflow-automations#analyze-employee-sentiment-and-provide-actionable-takeaways)

[Route each lead to the rep that's most likely to close the sale](https://www.merge.dev/blog/llm-powered-agents-intelligent-workflow-automations#route-each-lead-to-the-rep-thats-most-likely-to-close-the-sale)

[Deliver thoughtful and relevant gifts to new hires](https://www.merge.dev/blog/llm-powered-agents-intelligent-workflow-automations#deliver-thoughtful-and-relevant-gifts-to-new-hires)

[How to build function calls for Merge’s Unified API](https://www.merge.dev/blog/llm-powered-agents-intelligent-workflow-automations#how-to-build-function-calls-for-merges-unified-api)

[‍Final thoughts](https://www.merge.dev/blog/llm-powered-agents-intelligent-workflow-automations#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fllm-powered-agents-intelligent-workflow-automations)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c735d06bd38a725e7fb_Rate_limiting_best_practices.webp)**How data from product integrations can fuel cutting-edge AI features and products (3 real-world examples)**](https://www.merge.dev/blog/how-data-from-integrations-fuel-ai-features-and-products)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cafba04fd6de8974e02_AI_Blog.webp)**Powering AI with product integrations**](https://www.merge.dev/blog/powering-ai-with-product-integrations)

# How to use LLM-powered agents to build intelligent workflow automations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74f43703047123799f_Anthropic_API_key.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb26b36cc62374679f071f_Jon%20Gitlin%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd538684e09763589291b7_64c13599abc4a993825ecd2d_Jon%2520Gitlin%2520headshot.webp)

Jon Gitlin

Senior Content Marketing Manager

@Merge

The rise of LLMs has dramatically impacted how companies build and use product integrations.

We’ve seen customers feed the integration data they collect to their LLMs to produce more reliable outputs—leading them to provide a [wide range of cutting-edge AI features](https://www.merge.dev/blog/how-data-from-integrations-fuel-ai-features-and-products). And we use LLMs to power [Blueprint](https://www.merge.dev/campaigns/blueprint), which shows how third-party endpoints and fields are standardized to Merge's Common Models in seconds.

However, there’s another use case that you might find equally, if not more, valuable: using [OpenAI’s Function Calling](https://platform.openai.com/docs/guides/function-calling) feature to build LLM agents that drive intelligent integrations and automations.

The LLM agents can adapt to a wide range of events, making them valuable for seemingly any integration and automation scenario.

We’ll explore just a few of these scenarios so that you can get a better sense of their utility.

## **Address customer feedback effectively**

Let’s imagine that you offer a live chat product for communicating with customers. Let’s also assume that you’ve built several ticketing integrations to your product.

You can then build a semi-autonomous, LLM-powered agent that does the following: based on a chat conversation in your product, the LLM agent can decide whether to create a new ticket in the customer's ticketing tool and the level of urgency to assign the ticket.

Assuming the LLM agent decides to create a ticket, it can construct a POST ticket request to the customer's ticketing tool and include parameters like the level of priority for addressing the issue and a summary of the issue in the ticket’s description.

## **Analyze employee sentiment and provide actionable takeaways**

Let’s assume that you offer a survey tool that lets users get employee feedback and analyze the results.

To help customers send the right surveys to the right employees, you’ve connected to their HRIS solutions and synced their employee data. But by feeding a wide range of HRIS data to your LLM agent, such as previous survey responses, the amount of time employees have taken off, employees’ job titles, salaries, etc. your platform can suddenly become significantly more valuable.

Your LLM agent can arrive at a conclusion on the relative churn risk of a given employee and assign a specific score that underpins this risk. It can also add the reason(s) that led to its assessment.

The LLM agent can then go on to make POST requests to the customers’ HRIS systems to add the employees’ engagement scores and the reasons behind them. From there,  HR teams can quickly discover the feedback and prioritize their efforts accordingly.

_Related:_ [_The benefits of RAG_](https://www.merge.dev/blog/rag-benefits)

## **Route each lead to the rep that's most likely to close the sale**

Say you offer a marketing automation platform that can, among other things, route leads to sales teams.

To ensure that your platform sends leads to the reps that are most likely to close them, you build integrations with customers’ CRM systems and feed their historical opportunities to your LLM agent.

Your LLM agent can learn how quickly reps were able to close deals, how much they closed for, the specific products/service(s) customers bought, etc. The LLM agent can then retrieve additional information on the sales reps’ backgrounds (location, specific job title, etc.) by making API calls to a data enrichment tool like Zoominfo.

Based on all of the information the LLM agent retrieves, it can pinpoint the best rep for each lead. And once it has, it can make a POST request to the CRM system, where it adds the new lead, along with details like the rep that’s assigned to it.

## **Deliver thoughtful and relevant gifts to new hires**

Say you offer a gift-giving platform (like Snappy) and want to help users deliver gifts that are highly personalized.

To help your platform do this, you can integrate with customers’ HRIS solutions and feed your LLM agent information on the incoming hire, like their birthdate, location, gender, etc.

To get even more specific information, the LLM agent can scrape the web to find and learn from the incoming employee’s personal website, social media profiles, etc.

Once the LLM agent decides that it has enough information, it can provide users with tailored gift options to choose from and, for each, explain why it made the suggestion.

## **How to build function calls for Merge’s Unified API**

A critical step to implementing the use cases above—among countless others—involves your LLM agent being able to make API calls to Merge’s Unified API.

To enable this, you can provide the following code snippet to the LLM agent:

```python

import jsonref
import requests
from openai import OpenAI
import os
from pprint import pp
import json

MAX_CALLS = 5
MERGE_API_KEY = os.environ.get("MERGE_API_KEY", "")
client = OpenAI(api_key=os.environ.get("OPENAI_API_KEY", ""))

def filter_x_merge(obj):
    if isinstance(obj, dict):
        return {k: filter_x_merge(v) for k, v in obj.items() if not k.startswith("x-merge")}
    elif isinstance(obj, list):
        return [filter_x_merge(item) for item in obj]
    else:
        return obj

def openapi_to_functions(openapi_spec_url):
    response = requests.get(openapi_spec_url)
    openapi_spec = response.json()
    cleaned_spec = jsonref.JsonRef.replace_refs(openapi_spec)
    cleaned_spec = filter_x_merge(cleaned_spec)

    functions = []
    method_path_map = {}

    for path, methods in cleaned_spec["paths"].items():
        for method, spec_with_ref in methods.items():
            function_name = spec_with_ref.get("operationId")

            method_path_map[function_name] = (method.upper(), path)

            desc = spec_with_ref.get("description") or spec_with_ref.get("summary", "")

            schema = {"type": "object", "properties": {}}
            req_body = (spec_with_ref.get("requestBody", {})
                        .get("content", {})
                        .get("application/json", {})
                        .get("schema"))
            if req_body:
                filtered_req_body = {
                    k: v for k, v in req_body.get("properties", {}).items() if not k.startswith("x-merge")
                }
                json.dumps(filtered_req_body)
                schema["properties"]["requestBody"] = {
                    "type": "object",
                    "properties": filtered_req_body,
                }

            params = spec_with_ref.get("parameters", [])
            param_properties = {}
            for param in params:
                if "schema" in param and param["name"] != "X-Account-Token":
                    param_properties[param["name"]] = param["schema"]

            if param_properties:
                schema["properties"]["parameters"] = {
                    "type": "object",
                    "properties": param_properties,
                }

            functions.append({
                "type": "function",
                "function": {
                    "name": function_name,
                    "description": desc,
                    "parameters": schema
                }
            })

    return functions, method_path_map

def get_openai_response(functions, messages):
    return client.chat.completions.create(
        model="gpt-4-0125-preview",
        tools=functions,
        temperature=0,
        messages=messages,
    )

def make_api_call(function_name, category, account_token, method_path_map, **kwargs):
    headers = {"X-Account-Token": account_token, "Authorization": f"Bearer {MERGE_API_KEY}"}

    if function_name not in method_path_map:
        raise ValueError(f"Function {function_name} not recognized")

    method, path = method_path_map[function_name]
    url = f'https://api.merge.dev/api/{category}/v1{path}'

    query_params = kwargs.get('parameters', {})
    body = kwargs.get('requestBody', None)

    if method.upper() == 'GET':
        response = requests.get(url, headers=headers, params=query_params)
    elif method.upper() == 'POST':
        response = requests.post(url, headers=headers, json=body, params=query_params)
    elif method.upper() == 'PUT':
        response = requests.put(url, headers=headers, json=body, params=query_params)
    elif method.upper() == 'DELETE':
        response = requests.delete(url, headers=headers, params=query_params)
    else:
        raise ValueError(f"HTTP method {method} not supported")

    return response.json()

def process_user_instruction(functions, category, method_path_map, account_token, system_message, instruction):
    num_calls = 0
    messages = [\
        {"content": system_message, "role": "system"},\
        {"content": instruction, "role": "user"},\
    ]

    while num_calls < MAX_CALLS:
        response = get_openai_response(functions, messages)
        message = response.choices[0].message

        pp(message.tool_calls)
        messages.append(message)

        if not message.tool_calls:
            messages.append(
                {
                    "role": "system",
                    "content": message.content,
                }
            )
            break

        function = message.tool_calls[0].function
        function_args = function.arguments
        function_name = function.name

        messages.append(
            {
                "role": "tool",
                "content": "success",
                "tool_call_id": message.tool_calls[0].id,
            }
        )
        result = make_api_call(function_name, category, account_token, method_path_map, **json.loads(function_args))

        messages.append(
            {
                "role": "system",
                "content": f"API call successful. Result: {result}",
            }
        )

        num_calls += 1

    if num_calls >= MAX_CALLS:
        print(f"Reached max chained function calls: {MAX_CALLS}")

    return messages

def call_agent(category, account_token, system_message, user_instruction):
    functions, method_path_map = openapi_to_functions(f'https://api.merge.dev/api/{category}/v1/schema')

    messages = process_user_instruction(functions, category, method_path_map, account_token, system_message,
                            user_instruction)
    pp(messages)

```

And then give the LLM agent the following command:

_call\_agent("crm", account\_token, "You are an agent that constructs API calls to Merge's API. You will pull relevant information to make queries. You might need to pull additional information to help set up a query. Use filters as required.", "Get 3 opportunities in the open stage.")_

Note: You should replace “crm” with whatever category you want to build to and make the system prompt (“Get opportunities in the open stage.”) more specific and tailored to the problem you want your agent to solve.

The LLM agent can then spit out the following:

```python

[{'content': "You are an agent that constructs API calls to Merge's API. You "\
             'will pull relevant information to make queries. You might need '\
             'to pull additional information to help set up a query. Use '\
             'filters as required.',\
  'role': 'system'},\
 {'content': 'Get 3 opportunities in the qualifying stage.', 'role': 'user'},\
 ChatCompletionMessage(content=None, role='assistant', function_call=None, tool_calls=[ChatCompletionMessageToolCall(id='call_BoPzqNNGogPF9mUheJMop2Al', function=Function(arguments='{"parameters":{}}', name='stages_list'), type='function')]),\
 {'role': 'tool',\
  'content': 'success',\
  'tool_call_id': 'call_BoPzqNNGogPF9mUheJMop2Al'},\
 {'role': 'system',\
  'content': "API call successful. Result: {'next': None, 'previous': None, "\
             "'results': [... other stages,\
             "{'id': '02e94f6a-fe4f-4955-90ae-02ed8066180e', 'remote_id': "\
             "'01JDu000000idKvMAI', 'created_at': "\
             "'2024-03-26T23:50:10.195013Z', 'modified_at': "\
             "'2024-03-26T23:50:10.195018Z', 'name': '1 - Qualifying', "\
             "'remote_was_deleted': False, 'field_mappings': "\
             "{'organization_defined_targets': {}, "\
             "'linked_account_defined_targets': {}}, 'remote_data': None}, "\
           ... other stages]}"},\
 ChatCompletionMessage(content=None, role='assistant', function_call=None, tool_calls=[ChatCompletionMessageToolCall(id='call_8k0t8TqGgYPQuuoYYB2qgm77', function=Function(arguments='{"parameters":{"stage_id":"02e94f6a-fe4f-4955-90ae-02ed8066180e","page_size":3}}', name='opportunities_list'), type='function')]),\
 {'role': 'tool',\
  'content': 'success',\
  'tool_call_id': 'call_8k0t8TqGgYPQuuoYYB2qgm77'},\
 {'role': 'system',\
  'content': "API call successful. Result: {'next': "\
             "'cD0yMDI0LTAzLTI3KzE5JTNBMDQlM0EzNC4yNzcxNDclMkIwMCUzQTAw', "\
             "'previous': None, 'results': [{'id': "\
             "'41d78e95-ec20-4f0d-91d2-6ac54f93c223', 'remote_id': "\
             "'006Em000004YkffIAC', 'created_at': "\
             "'2024-03-27T19:04:34.277605Z', 'modified_at': "\
             "'2024-03-27T19:04:34.277610Z', 'name': 'Acme Corporation-5/2023-New Business', 'description': '', 'amount': None, "\
             "'owner': None, 'account': None, 'stage': "\
             "'02e94f6a-fe4f-4955-90ae-02ed8066180e', 'status': 'OPEN', "\
             "'last_activity_at': None, 'close_date': '2023-05-01T00:00:00Z', "\
             "'remote_created_at': '2023-07-26T15:07:19Z', "\
             "'remote_was_deleted': False, 'field_mappings': "\
             "{'organization_defined_targets': {}, "\
             "'linked_account_defined_targets': {}}, 'remote_data': None}, "\
             ... the other opportunities]}"},\
 {'role': 'system',\
  'content': 'Here are 3 opportunities in the qualifying stage:\n'\
             '\n'\
             '1. **Acme Corporation-5/2023-New Business\n'\
             '   - ID: 41d78e95-ec20-4f0d-91d2-6ac54f93c223\n'\
             '   - Close Date: 2023-05-01\n'\
             '   - Stage: Qualifying\n'\
             '\n'\
             ... the other opportunities}]

```

## ‍ **Final thoughts**

Your LLM agents can use function calling to support a wide range of complex and impactful processes through retrieving information, problem solving based on that information, and then performing the relevant set of actions.

The organizations that use these agents in the most creative, high-impact ways for their product are likely to build competitive moats that’ll last for years to come.

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e3d48044-8ffb-4505-a723-d061b6f23624&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=a71cfc85-c5bd-4461-81e7-49ec4079d00f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fllm-powered-agents-intelligent-workflow-automations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=e3d48044-8ffb-4505-a723-d061b6f23624&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=a71cfc85-c5bd-4461-81e7-49ec4079d00f&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fllm-powered-agents-intelligent-workflow-automations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=0b0680c8-26e8-4fce-8fff-9627bae05cce&bo=2&sid=50a062d03e8e11f0a32d75ba31c5b1dd&vid=50a0f4203e8e11f0b9daedfcf2e355f6&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=How%20to%20use%20LLM-powered%20agents%20to%20build%20intelligent%20workflow%20automations&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fllm-powered-agents-intelligent-workflow-automations&r=&lt=460&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=928640)