---
url: "https://www.merge.dev/blog/how-to-build-mcp-server"
title: "3 steps to build an MCP server from scratch"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-build-mcp-server#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-build-mcp-server#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-build-mcp-server#)

Table of contents

[Overview on the Model Context Protocol](https://www.merge.dev/blog/how-to-build-mcp-server#overview-on-the-model-context-protocol)

[How to build an MCP server](https://www.merge.dev/blog/how-to-build-mcp-server#how-to-build-an-mcp-server)

[Does your LLM need to access customer data at scale?](https://www.merge.dev/blog/how-to-build-mcp-server#does-your-llm-need-to-access-customer-data-at-scale)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-build-mcp-server)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**AI connectors: use cases, benefits, and features**](https://www.merge.dev/blog/ai-connector)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d857c228f210c3289347ec_Blog%20Header%20Brand%20Refresh%20(5).png)**The hidden security threats of MCP—and how to mitigate them**](https://www.merge.dev/blog/model-context-protocol-security)

# 3 steps to build an MCP server from scratch

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67ffc161529060fb1994a3c2_MCP%20server%20guide.png)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67caee40ccdc6ec829d415d3_David%20Dalmaso%20-%20Merge-min.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/679bc329176d8ae0120289e6_Group%2037286.webp)

David Dalmaso

Engineer

@Merge

If you work with and sell to companies in the AI industry, you’re likely receiving requests to support the Model Context Protocol (MCP) through an MCP server.

Your MCP server would allow any large language model (LLMs) to easily access data and functionality in your product, which an LLM can then use to complete key workflows for customers.

But the process of building a robust, production-ready MCP server isn’t straightforward.

To help you implement yours faster and more easily, I’ll walk you through the steps you’ll need to take based on my experience in building our own MCP server— [Merge MCP](https://www.merge.dev/features/mcp).

But first, let’s align on the core elements of [the Model Context Protocol](https://www.merge.dev/blog/model-context-protocol).

#### Ready to connect your LLM to hundreds of applications?

Learn how Merge MCP can support all your customer-facing integrations by connecting with our team.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-build-mcp-server)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Overview on the Model Context Protocol**

At its core, MCP consists of tools, a call\_tool function, and a list\_tool function.

- **A tool** executes predefined functions on behalf of an LLM. It includes a name, a description, which outlines how the function works, and an input schema, which lays out the required and optional parameters you can pass

For example, here’s how the input schema looks for the Merge MCP file\_retrieval function:

```python
{
   "type":"object",
   "properties":{
      "expand":{
         "expand":{
            "type":"string",
            "description":"Which relations should be returned in expanded form. Multiple relation names should be comma separated without spaces.",
            "in":"query",
            "enum":[\
               "drive",\
               "folder",\
               "folder,drive",\
               "permissions",\
               "permissions,drive",\
               "permissions,folder",\
               "permissions,folder,drive"\
            ]
         }
      },
      "id":{
         "id":{
            "type":"string",
            "description":"The ID of the file to retrieve.",
            "in":"path",
            "format":"uuid"
         }
      }
   },
   "required":[\
      "id"\
   ]
}

```

- **The list\_tool function** lets your users discover all the tools you provide in your MCP server via a tools/list endpoint. Also, depending on your implementation, it can provide important context on a given tool, such as the specific actions it performs

[![A screenshot of some of the available tools for Merge MCP](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67ffbb1243c607e032ffe629_AD_4nXcwRbYvGUSypciK5-5jhhKn9nO2BKyAP2f7-ST3n6fcBF_vBqumYIR8ji2_P9n5U_pySV2zbcbIm04ms33Z4z2nx7qh8i-IpL7bAAC1rry-eM6x5aXZMM63AVqfKz6UhI5xi7iwuA.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67ffbb1243c607e032ffe629_AD_4nXcwRbYvGUSypciK5-5jhhKn9nO2BKyAP2f7-ST3n6fcBF_vBqumYIR8ji2_P9n5U_pySV2zbcbIm04ms33Z4z2nx7qh8i-IpL7bAAC1rry-eM6x5aXZMM63AVqfKz6UhI5xi7iwuA.png)

_Merge MCP, our newly-released MCP server, lets our customers’ customers (i.e., end users) easily discover tools in our server via the list\_tools function_

- **The call\_tool function** invokes a specific tool in an MCP server

In most cases, your users would see the tools available in the list\_tool function before deciding on the tool they use for the call\_tool function.

Once a tool is selected, the LLM populates its name and parameters in the call\_tool function, and the call\_tool function would go on to perform the predefined action (e.g., making an API request).

For example, here’s the call\_tool function for the Merge MCP file\_retrieval function:

```python

call_tool(name="files_retrieve", arguments={
  `id`: `f12a306a-1d1a-4148-a89e-1f47a95c3459`,
  `expand`: `folder,drive`
})

```

[https://www.merge.dev/blog/api-vs-mcp?blog-related=image](https://www.merge.dev/blog/api-vs-mcp?blog-related=image)

## **How to build an MCP server**

Building an MCP server requires building both the list\_tool and call\_tool functions.

The steps for implementing each function depend on the type of MCP server you’re supporting, but here are the steps we took to build Merge MCP and that you need to take to build your own server.

### **1\. Set up your MCP server**

Establishing the server requires adding just a few lines of code.

For example, to build an MCP server via Python, you can use the following code:

```python

from typing import List, Sequence

from mcp.server import Server
from mcp.server.stdio import stdio_server
from mcp.types import EmbeddedResource, ImageContent, TextContent, Tool

async def serve(scopes: List[str] | None = None) -> None:
    server = Server("mcp")

    @server.list_tools()
    async def list_tools() -> List[Tool]:
        """List available MCP tools."""
        return []

    @server.call_tool()
    async def call_tool(
        name: str, arguments: dict
    ) -> Sequence[TextContent | ImageContent | EmbeddedResource]:
        """Handle tool calls for MCP tools."""
        return [\
                TextContent(\
                    type="text",\
                    text=f"Successfully called {name}",\
                )\
            ]

    options = server.create_initialization_options()
    async with stdio_server() as (read_stream, write_stream):
        await server.run(read_stream, write_stream, options)

def main():
    import asyncio

    asyncio.run(serve())

if __name__ == "__main__":
    main()

```

When we implemented Merge MCP’s server, we also included Merge API Token and Merge Account Key fields so that our end users (our customers’ customers) can access our customers’ integrations securely.

### **2\. Implement a list\_tool function**

You can implement this in one of two ways:

- **Directly define the function within your MCP server and tag it as a tool.** MCP can then define the schema on your behalf and add it to your list\_tool endpoint

For example, the [MCP quickstart guide](https://modelcontextprotocol.io/quickstart/server#python) outlined the code you can use to define two functions—get\_alerts and get\_forecast—within an MCP server.

```python

@mcp.tool()
async def get_alerts(state: str) -> str:
    """Get weather alerts for a US state.

    Args:
        state: Two-letter US state code (e.g. CA, NY)
    """
    url = f"{NWS_API_BASE}/alerts/active/area/{state}"
    data = await make_nws_request(url)

    if not data or "features" not in data:
        return "Unable to fetch alerts or no alerts found."

    if not data["features"]:
        return "No active alerts for this state."

    alerts = [format_alert(feature) for feature in data["features"]]
    return "\n---\n".join(alerts)

@mcp.tool()
async def get_forecast(latitude: float, longitude: float) -> str:
    """Get weather forecast for a location.

    Args:
        latitude: Latitude of the location
        longitude: Longitude of the location
    """
    # First get the forecast grid endpoint
    points_url = f"{NWS_API_BASE}/points/{latitude},{longitude}"
    points_data = await make_nws_request(points_url)

    if not points_data:
        return "Unable to fetch forecast data for this location."

    # Get the forecast URL from the points response
    forecast_url = points_data["properties"]["forecast"]
    forecast_data = await make_nws_request(forecast_url)

    if not forecast_data:
        return "Unable to fetch detailed forecast."

    # Format the periods into a readable forecast
    periods = forecast_data["properties"]["periods"]
    forecasts = []
    for period in periods[:5]:  # Only show next 5 periods
        forecast = f"""
{period['name']}:
Temperature: {period['temperature']}°{period['temperatureUnit']}
Wind: {period['windSpeed']} {period['windDirection']}
Forecast: {period['detailedForecast']}
"""
        forecasts.append(forecast)

    return "\n---\n".join(forecasts)

```

This works great when your function is static. For example, if, hypothetically, your MCP server consists of API endpoints that won’t change.

- **Explicitly define schemas for tools and return the schemas.** These schemas won’t be mapped to specific functions (e.g., API endpoints), but they can provide enough information on a tool's function

Since we’re constantly adding to and improving our endpoints, we opted for this approach when building Merge MCP.

For example, if one of your users wants to create tickets in their project management system via Merge MCP, they can input something like:

“Can you create me a ticket called ‘\[BUG\] Google Auth sign in broken" that is high priority?’”

The LLM can then identify the appropriate tool—ticket\_create—and use the predefined schema to ensure all the necessary information is properly formatted and validated before making the request.

Here’s how this can look for the user:

[![A screenshot of a ticket_create response from Merge MCP](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67ffbb11a2718ad995802ca7_AD_4nXfT2zxpSAT3S6_Ms684XRbj1NfMjz5rwKZXuVeS5Kh3qxL6FlYe4_NJ4d44QUkqNJMjCw_YjEcYKE17b5zGYgdtru3UYg9hrKTjUXDnDVCV5uKaFtvxEJtsp_wopYcXIUCjmwuWkw.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67ffbb11a2718ad995802ca7_AD_4nXfT2zxpSAT3S6_Ms684XRbj1NfMjz5rwKZXuVeS5Kh3qxL6FlYe4_NJ4d44QUkqNJMjCw_YjEcYKE17b5zGYgdtru3UYg9hrKTjUXDnDVCV5uKaFtvxEJtsp_wopYcXIUCjmwuWkw.png)

[https://www.merge.dev/blog/mcp-best-practices?blog-related=image](https://www.merge.dev/blog/mcp-best-practices?blog-related=image)

### **3\. Build your call\_tool function**

Assuming your tools map to API endpoints listed on an OpenAPI schema, you’ll need to look up the OpenAPI spec parameters for each tool.

From there, you can construct the endpoint, any query parameters (if applicable), and the body of the request (if applicable) from the given arguments. You can then make a live API call.

You should also pass along the API call’s output with what you provided in the request so that the function can include detailed messages when the call\_tool function succeeds and when it fails. That way, your LLM knows how to handle the data, whether that’s making a follow-up request that addresses the previous issue or it’s sharing the parameters from a successful request with the user.

As part of this step, you’ll also want to sanitize the data so that you’re not passing along any sensitive information.

[![How an LLM can take additional steps if its initial request isn’t successful](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67ffbb12179712fec92387bb_AD_4nXfRhrPZnFzkJAbs7WaQynkASc6bOLC5K02JFkzWAE1t29rY2yn7xnBLDtpWgmGZy62q8XVVtrG1W2oJzJL_DisRA9MOFodFVWNtLSBowTOdlLF4yhManXIEVw-h0IyXv5Qn7j7qog.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67ffbb12179712fec92387bb_AD_4nXfRhrPZnFzkJAbs7WaQynkASc6bOLC5K02JFkzWAE1t29rY2yn7xnBLDtpWgmGZy62q8XVVtrG1W2oJzJL_DisRA9MOFodFVWNtLSBowTOdlLF4yhManXIEVw-h0IyXv5Qn7j7qog.png)

_How an LLM can take additional steps if its initial request isn’t successful_

Once this is set up, the LLM picks a tool and sets up the arguments on the client side. It then passes the tool’s name and arguments to the call\_tool function, which invokes the appropriate action.

[https://www.merge.dev/blog/rag-vs-mcp?blog-related=image](https://www.merge.dev/blog/rag-vs-mcp?blog-related=image)

## **Does your LLM need to access customer data at scale?**

Merge MCP lets your LLM access 220+ applications securely, reliably, and quickly (you’ll just need to write a few lines of code!) to support all of your product’s AI use cases.

Merge also:

- Provides [Integration Observability features](https://www.merge.dev/features/integration-observability) to help your customer-facing teams manage the integrations

- Normalizes the integrated data according to its predefined data models ( [“Common Models”](https://www.merge.dev/features/common-models)) to help your LLM generate accurate, non-sensitive outputs consistently

- Offers advanced syncing features (e.g., [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/)) to help your LLM access custom data

You can learn more about Merge MCP by [scheduling a demo with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-build-mcp-server) and by watching our demo walkthrough below!

Merge Model Context Protocol (MCP) Demo - YouTube

Merge

202 subscribers

[Merge Model Context Protocol (MCP) Demo](https://www.youtube.com/watch?v=IsMoqV13Seo)

Merge

Search

Info

Shopping

Tap to unmute

If playback doesn't begin shortly, try restarting your device.

You're signed out

Videos you watch may be added to the TV's watch history and influence TV recommendations. To avoid this, cancel and sign in to YouTube on your computer.

CancelConfirm

Share

Include playlist

An error occurred while retrieving sharing information. Please try again later.

Watch later

Share

Copy link

Watch on

0:00

/
•Live

•

[Watch on YouTube](https://www.youtube.com/watch?v=IsMoqV13Seo "Watch on YouTube")

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67caee40ccdc6ec829d415d3_David%20Dalmaso%20-%20Merge-min.png)

David Dalmaso

Engineer

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