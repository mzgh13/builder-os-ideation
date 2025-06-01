---
url: "https://www.merge.dev/blog/api-pagination-challenges-for-multiple-integrations"
title: "Top challenges of API pagination for multiple integrations"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/api-pagination-challenges-for-multiple-integrations#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/api-pagination-challenges-for-multiple-integrations#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/api-pagination-challenges-for-multiple-integrations#)

Table of contents

[What is API pagination?](https://www.merge.dev/blog/api-pagination-challenges-for-multiple-integrations#what-is-api-pagination)

[The different types of API pagination](https://www.merge.dev/blog/api-pagination-challenges-for-multiple-integrations#the-different-types-of-api-pagination)

[The challenges of supporting pagination for multiple APIs](https://www.merge.dev/blog/api-pagination-challenges-for-multiple-integrations#the-challenges-of-supporting-pagination-for-multiple-apis)

[A simple solution to pagination for multiple APIs—Merge](https://www.merge.dev/blog/api-pagination-challenges-for-multiple-integrations#a-simple-solution-to-pagination-for-multiple-apismerge)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-pagination-challenges-for-multiple-integrations)

##### Just for you

No items found.

# Top challenges of API pagination for multiple integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74fb72017b567d9265_RAG_benefits.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb29671db3f6dae74b6234_Anthony%20Lagana%20-%20Merge.png)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/652f075d8a58040737ed01ab_anthony-lagana-4x.webp)

Anthony Lagana

Product Marketing

@Merge

Just like how humans divide up written content into pages, software APIs use pagination to digest large quantities of data.

But 3rd-party APIs often use varying forms of pagination depending on when they were produced or the type of data that’s being returned. accommodating to these various approaches can, in and of itself, complicate your integration builds quickly.

We’ll explore this issue further and break down a solution for overcoming this challenge. But first, let’s explore what API pagination means and the different types of API pagination you might come across.

## What is API pagination?

It's the process of dividing a large dataset into smaller, discrete parts or 'pages' to make accessing and managing large volumes of data more efficient. This approach is particularly useful for improving the user experience in browsing large lists or datasets, as it reduces load times and data overload.

For example, you may want to GET data from 10,000 employee records. But receiving such a high volume of data at once can cause performance issues, such as lengthy data loads. Pagination makes it so that those records aren’t returned all at once; instead, records are batched in ‘pages’ that you can access programmatically.

_Related:_ [_What is multiple API integration?_](https://www.merge.dev/blog/multiple-api-integration)

## The different types of API pagination

Let's take a closer look at the different versions of pagination.

### 1\. Cursor pagination

[Cursor pagination](https://www.merge.dev/blog/cursor-pagination) is like reading a book with a bookmark. It allows the client to request data in a sequence and uses a 'cursor' to keep track of its position. This cursor is often a unique identifier (like an ID or timestamp) of the last item from the previous request.

This approach is incredibly efficient for real-time data and large datasets because it reduces the load on the server and provides a consistent user experience.

#### What does cursor pagination look like in code?

```python

from flask import request

@app.route('/items')

def get_items():

    cursor = request.args.get('cursor', default=None)

    limit = int(request.args.get('limit', default=10))

    query = Item.query.order_by(Item.id)

    if cursor:

        query = query.filter(Item.id > cursor)

    items = query.limit(limit).all()

    next_cursor = items[-1].id if items else None

    return jsonify({'items': [item.to_dict() for item in items], 'next_cursor': next_cursor})

```

This code helps show a large list of items in smaller, numbered sections, and keeps track of where you are in the list.

1. Getting parameters: The code starts by checking for two pieces of information given by the user—where to start in the list (cursor) and how many items to show (limit).
2. Fetching data with limits: It then gets a set of items from a database, but only a specific number at a time, as determined by the limit. If a cursor is given, it starts from the item after the cursor.
3. Determining the next starting point: After getting these items, the code figures out what the starting point (next\_cursor) should be for the next time someone asks for more items.
4. Sending the data back: Finally, the code sends back the list of items it got, along with the next\_cursor, so the user knows where to start next time to get more items.

### 2\. Offset pagination

Offset pagination involves specifying a starting point (the offset) and the number of records to retrieve (the limit). For example, offset=10&limit=10 would skip the first 10 records and return the next 10.

#### What does offset pagination look like in code?

```python

from flask import request

@app.route('/items') def get_items(): page = int(request.args.get('page', default=1)) limit = int(request.args.get('limit', default=10)) offset = (page - 1) * limit

items = Item.query.offset(offset).limit(limit).all()

return jsonify({'items': [item.to_dict() for item in items]})

```

This code allows a user to request specific "pages" of data from a list, each containing a set number of items. The page and limit help in dividing the entire list into smaller, more manageable sections.

1\. Getting page and limit: The code looks for two pieces of information from the user—which page of items they want to see (page) and how many items should be on each page (limit).

2\. Calculating the offset: It calculates the offset, which is basically the number of items to skip before starting to show items on the requested page. This is done by multiplying the page number by the limit and subtracting the limit.

3\. Fetching the data: The code then gets the items from the database, starting from the calculated offset and fetching up to the limit number of items.

4\. Sending the items back: Lastly, it sends back the fetched items in a format that's easy to use (like a list of item details).

_Related:_ [_The top challenges of integrating software_](https://www.merge.dev/blog/software-integration-challenges)

### 3\. Keyset pagination

[Keyset pagination](https://www.merge.dev/blog/keyset-pagination), sometimes called 'seek' pagination, is a bit like using a ruler to keep your place in a list. It involves selecting records where a certain field (the keyset) is greater or less than the value from the last retrieved row. This method is efficient for large datasets and works well when sorting by a unique, sequential field like a timestamp or an auto-incrementing ID.

#### What does keyset pagination look like in code?

```python

from flask import request

@app.route('/items') def get_items(): last_id = request.args.get('last_id', default=None) limit = int(request.args.get('limit', default=10))

query = Item.query

if last_id:
    query = query.filter(Item.id > last_id)

items = query.order_by(Item.id).limit(limit).all()

return jsonify({'items': [item.to_dict() for item in items]})

```

This code helps show a big list in smaller parts, one chunk at a time, and remembers where it stopped last so it can continue from there next time.

1\. Starting point: The code looks for a last\_id which tells it where it left off last time. If there's no last\_id, it starts from the beginning.

2\. How many to show: It also checks how many items to display at once (limit), which is set to 10 by default.

3\. Getting the items: The code then gets the items from the list, starting after the last\_id (if there is one), and only takes as many as the limit.

4\. Sending the list back: Finally, it sends this list of items back to whoever asked for it.

### 4\. Seek pagination

Seek pagination is akin to using a combination of bookmarks and a table of contents in a book. It typically involves using a unique field (or a combination of fields) to directly seek a position in the dataset, rather than incrementally navigating through it. This method is particularly useful when dealing with very large datasets and when the client knows exactly where to jump in the dataset.

#### What does seek pagination look like in code?

```python

from flask import request

@app.route('/items') def get_items(): seek_id = request.args.get('seek_id', default=None) limit = int(request.args.get('limit', default=10))

query = Item.query
if seek_id:
    query = query.filter(Item.id == seek_id)

items = query.limit(limit).all()

return jsonify({'items': [item.to_dict() for item in items]})

```

This code helps users either get a bunch of items from a list, limited to a certain number, or start from a specific item and get a limited number of items from there.

1\. What it does: This code sets up a way for users to get a list of items from a database, but with a limit on how many items they can see at once.

2\. Starting point (seek\_id): Users can provide a seek\_id, which is like asking, "Can I see the item that has this specific ID?" If they provide this ID, the code will look for items starting from that specific item.

3\. Limiting the number of items: There's a limit on how many items the user can get at once, which is set to 10 unless the user specifies a different number.

4\. Fetching and sending the items: The code then gets the items according to these instructions (starting at seek\_id if given, and up to the limit number of items). It sends back these items in a format that's easy to use.

_Related:_ [_How to calculate the costs of an API integration_](https://www.merge.dev/blog/cost-of-api-integrations)

### 5\. Time-based pagination

Time-based pagination is like reading a diary, where you flip through pages based on dates. It's ideal for datasets where entries are time-stamped and the user is interested in viewing records from a specific period.

This approach is common in applications that deal with logs, historical data, or real-time feeds where temporal context is important.

#### What does time-based pagination look like in code?

```python

from flask import request
from datetime import datetime

@app.route('/items')
def get_items():
    start_time = request.args.get('start_time')
    end_time = request.args.get('end_time', default=datetime.now())
    limit = int(request.args.get('limit', default=10))

    query = Item.query
    if start_time:
        query = query.filter(Item.timestamp >= start_time)
    if end_time:
        query = query.filter(Item.timestamp <= end_time)

    items = query.limit(limit).all()

    return jsonify({'items': [item.to_dict() for item in items]})

```

In essence, this function is for getting a specific number of items from a list, where those items fall within a certain time range specified by the user.

1\. Time filters: The function allows users to specify a start\_time and an end\_time to filter items. These items have timestamps associated with them.

- If a start\_time is provided, the function will look for items with timestamps on or after this time.
- end\_time defaults to the current time (right now) if not specified. The function will look for items with timestamps up to and including this time.

2\. Limiting the number of items: There's also a limit on how many items can be retrieved at once. By default, it's set to 10, but users can specify a different limit.

3\. Fetching the items: The function then runs a database query to get the items that match the time criteria and limits the result to the specified number of items.

4\. Sending the results back: Finally, it sends the list of retrieved items back in a format that's easy to understand and use, which is likely a JSON response.

### 6\. Page number pagination

Page number pagination is like using a traditional index in a book. Users specify the exact page number they wish to access. This method is straightforward and user-friendly, especially for datasets where the total number of pages is known and not excessively large.

#### What does Page Number Pagination look like in code?

```python

from flask import request

@app.route('/items')
def get_items():
    page_number = int(request.args.get('page_number', default=1))
    limit = int(request.args.get('limit', default=10))
    offset = (page_number - 1) * limit

    items = Item.query.offset(offset).limit(limit).all()

    return jsonify({'items': [item.to_dict() for item in items]})

```

In short, this code helps users see parts of a big list, a set number of items at a time, and lets them choose which part to see.

1\. Choosing the page: The user can pick which page of items they want to see, like page 1, page 2, and so on. If they don't choose, it shows the first page.

2\. How many Items on a page:It also lets the user decide how many items should be on each page. If they don't say, it shows 10 items per page.

3\. Finding the starting point: The code calculates where to start showing items for the chosen page. For example, on page 2, it skips the first 10 items (if there are 10 items per page) and starts from item 11.

4\. Getting the items: Then it gets the right amount of items from the list, starting from where it was calculated.

5\. Sending the list back: Finally, it sends this list of items back to the user.

_Related:_ [_Software integration best practices_](https://www.merge.dev/blog/software-integration-best-practices)

## The challenges of supporting pagination for multiple APIs

As you look to scale the number of integrations you build and maintain, you might find challenges in dealing with the APIs' varied approaches to pagination. Here are a few to keep in mind:

### **Accounting for diverse pagination methods**

APIs use various pagination methods, like page-based, cursor-based, offset-limit, or time-based. Aligning these differing approaches into a single, consistent pagination model for your application can be complex. This involves understanding and adapting to each API's unique method while maintaining a seamless experience for your application's users.

### Accommodating large volumes of data

As your application scales, you'll likely encounter massive volumes of data. Efficiently processing, storing, and querying millions of data objects without performance degradation is a substantial challenge. This includes ensuring that pagination doesn't become a bottleneck in data retrieval and processing.

### Minimizing costs without sacrificing performance

Different APIs may impose varying limits on page sizes and data retrieval rates. You must balance these limits to optimize data fetching, minimize API calls, and ensure a responsive user experience.

This balancing act requires smart caching strategies, efficient batch processing, and adept asynchronous data handling.

### Handling API rate limits and quotas

Many APIs impose rate limits and data quotas. When your application relies on multiple APIs, managing these limits becomes complex. You need to ensure that your pagination strategy doesn't lead to excessive API calls that might exceed these limits, leading to potential service disruptions or additional costs.

### User experience uniformity

Maintaining a consistent and intuitive user experience can be challenging when integrating multiple pagination methods. Users should feel a seamless experience regardless of the underlying pagination mechanism.

## **A simple solution to pagination for multiple APIs—Merge**

Rather than building out your own pagination architecture, Merge provides a single form of pagination to interact with data from its 180+ integrations.

Merge uses cursor pagination, and pagination is specified via the cursor and page\_size query parameters. The next and previous cursors are attached to paginated API responses. Their values inform the cursor where to point to next. You can learn more about our approach to pagination [in our docs](https://docs.merge.dev/basics/pagination/).

In addition to unified pagination, Merge also handles rate limits, offers a set of unified Common Data Models, and more.

Wondering how Merge can support your integration strategy? You can find out by [connecting with one of our integration experts](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fapi-pagination-challenges-for-multiple-integrations)!

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cb29671db3f6dae74b6234_Anthony%20Lagana%20-%20Merge.png)

Anthony Lagana

Product Marketing

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8aeaeac1-4383-467a-af52-68bbf7250cf7&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=73a93004-97e9-4890-a76f-4590687b601a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-pagination-challenges-for-multiple-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=8aeaeac1-4383-467a-af52-68bbf7250cf7&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=73a93004-97e9-4890-a76f-4590687b601a&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-pagination-challenges-for-multiple-integrations&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=b609c417-2233-4d05-88ab-e390b697d7bb&bo=2&sid=6f783f603e8d11f0bb81abb6d7e7dd70&vid=6f784bd03e8d11f08e22ffdd06c01faa&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Top%20challenges%20of%20API%20pagination%20for%20multiple%20integrations&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fapi-pagination-challenges-for-multiple-integrations&r=&lt=480&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=346289)