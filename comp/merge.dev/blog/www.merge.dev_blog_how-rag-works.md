---
url: "https://www.merge.dev/blog/how-rag-works"
title: "A guide on how retrieval-augmented generation (RAG) works"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-rag-works#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-rag-works#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-rag-works#)

Table of contents

[Understanding RAG](https://www.merge.dev/blog/how-rag-works#understanding-rag)

[Final thoughts](https://www.merge.dev/blog/how-rag-works#final-thoughts)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-rag-works)

##### Just for you

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**9 powerful examples of retrieval-augmented generation (RAG)**](https://www.merge.dev/blog/rag-examples)

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67cdd376071b615c9f2dcbcb_Blog%20Header%20Brand%20Refresh.png)**5 benefits of retrieval-augmented generation (RAG)**](https://www.merge.dev/blog/rag-benefits)

# A guide on how retrieval-augmented generation (RAG) works

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67e1d62e9de3c53196a2ee32_Blog%20Header%20Brand%20Refresh%20(7).png)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)

Alen Kalac

@Merge

Large language models (LLMs) are widely popular and extremely useful, but they also have some notable flaws.

Because they haven't been pretrained on new data, they don't have knowledge of current events. They can also give inaccurate answers (i.e., hallucinate), and they have little or no knowledge specific to your organization.

Retrieval-augmented generation (RAG) is a technique that can overcome these gaps by letting LLMs pull up-to-date, relevant information from internal or external sources.

With RAG, LLMs aren't limited to what they were originally trained on—they can access new data in real time, including news, domain-specific knowledge, or even private company data.

Here’s more on how RAG works and how it can help your organization leverage LLMs effectively.

#### Ready to build best-in-class AI features?

Merge lets you access all the customer data you need to power best-in-class RAG pipelines.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-rag-works)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

## **Understanding RAG**

RAG lets you augment an LLM's capabilities by connecting it to sources of external knowledge. To make that possible, RAG's architecture consists of many different components that work together in a specific way.

[![How RAG works](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/681393c14493777902d8fcd2_AD_4nXc0m_PFleutE5CW2s2UM6hArZ5Fq8tsrLHISaHBEUBMAlUYmErvWyMY3ODzQEXTvsmTkKWH14F-DvJfPukNGII5kfIsTZUKMSO-7-6r1wuLxxlgsQt3w8K_V_0f6PosYN9fhcqNmA.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/681393c14493777902d8fcd2_AD_4nXc0m_PFleutE5CW2s2UM6hArZ5Fq8tsrLHISaHBEUBMAlUYmErvWyMY3ODzQEXTvsmTkKWH14F-DvJfPukNGII5kfIsTZUKMSO-7-6r1wuLxxlgsQt3w8K_V_0f6PosYN9fhcqNmA.png)

Let's take a closer look at these components and how they fit together.

### **Data sources and knowledge base**

The initial step in implementing RAG is collecting data and creating a knowledge base.

The knowledge base can contain both structured and unstructured data:

- **Structured data** is organized in a predefined format, like rows and columns, which makes it easy to search and analyze. Common sources include relational databases, knowledge graphs, APIs, and data warehouses **‍**

- **Unstructured data** lacks a fixed structure and can be found in text documents, web content, vector databases, and multimedia files.

You can collect and store this data in various formats, such as PDF, CSV, or HTML files.

In addition to the knowledge base you create, RAG can also tap into real-time data, like streaming data sources or APIs. To do this effectively, you need a reliable external source of data.

Regardless of the data source, the data you feed to RAG needs to be high quality. As with all machine learning (ML), the classic adage "garbage in, garbage out" applies to RAG as well.

[Related](https://www.merge.dev/blog/rag-vs-mcp?blog-related=image)

#### [MCP vs RAG: how they overlap and differ](https://www.merge.dev/blog/rag-vs-mcp?blog-related=image)

[![MCP vs RAG: how they overlap and differ](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d857c228f210c3289347ec_Blog%20Header%20Brand%20Refresh%20(5).png)](https://www.merge.dev/blog/rag-vs-mcp?blog-related=image)

### **Document preprocessing**

Once the data is collected, it has to be preprocessed and transformed into a usable format. This preprocessing stage can cover many steps, including data cleaning, chunking, tokenization, and adding metadata.

Data that’s not properly preprocessed can lead to problems later in the process, such as retrieving irrelevant data.

The primary thing you need to do is ensure that the data is in the same format. Then, you should perform a series of steps to clean the data, such as removing unnecessary characters and blank lines, stripping HTML tags, and removing unnecessary whitespaces. You can also [tokenize](https://www.geeksforgeeks.org/nlp-how-tokenizing-text-sentence-words-works/) the documents, which involves splitting the text into tokens, such as words or phrases. This makes processing the text easier.

A very important step to perform is _chunking_. Since LLMs have a limited context size, they can't process large documents in one go. To work around this, the documents must be chunked into smaller pieces. Adding metadata can also be helpful—it provides extra context that can improve retrieval accuracy later on.

### **Embeddings and vector databases**

Even after the text documents have been preprocessed, they're still not ready to be used for RAG.

You have to transform the text into numbers that a machine can understand. This process of transformation is called embedding. Through embedding, every word or sentence in the document is transformed into a vector representation.

Since every word in a document can be transformed into a separate vector, you have to store a large number of vectors and quickly search through them to retrieve the relevant information. In general, traditional databases lack the specialized indexing ability and the algorithms required for a fast, large-scale semantic similarity search. That's why they're not an ideal choice when it comes to working with a large number of vectors.

In comparison, vector databases can store a huge number of vectors, are highly scalable, and, perhaps most importantly, can quickly search through all the document embeddings and find the most relevant pieces of information. It's important to note that vector databases can retrieve information based on semantic similarity and not just based on simple distance metrics.

### **Retrieval mechanisms**

There are multiple techniques when it comes to fetching useful data from the vector database.

#### **Sparse retrieval**

This method uses token-based representations; documents are represented as sparse vectors, whereas text is represented as high-dimensional vectors with most dimensions equal to zero, indicating the absence of certain features.

Sparse retrieval leverages keyword matching, with the retrieval being based on the exact occurrence of the terms within the query. It's relatively simple to implement and isn't computationally expensive, which makes it a good choice for basic use cases.

#### **Dense retrieval**

The sparse retrieval method is inferior compared to more modern approaches, like dense retrieval, which uses dense vector embeddings, usually generated with transformer-based models like the bidirectional encoder representations from transformers (BERT).

Dense retrieval also maps text into vectors, but it can capture semantic meaning and perform semantic search. This allows retrieval based on the query's meaning and not just based on the keywords. As a result, it yields higher-quality results, particularly when the meaning and context matter. However, it's important to note that dense retrieval is more computationally expensive.

#### **Hybrid retrieval**

You can also go with a hybrid retrieval approach, which combines sparse and dense retrieval methods. In general, the sparse retrieval method is used for keyword-based matching, while the dense retrieval method is used for semantic search. However, a hybrid approach adds a layer of complexity, both in terms of development and maintenance.

[Related](https://www.merge.dev/blog/rag-tools?blog-related=image)

#### [Best RAG tools to improve accuracy and personalization](https://www.merge.dev/blog/rag-tools?blog-related=image)

[![Best RAG tools to improve accuracy and personalization](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67e17bedb1db19c2e51d5aa5_Apideckpricing.png)](https://www.merge.dev/blog/rag-tools?blog-related=image)

### **Context processing**

The information retrieved from the knowledge base is often referred to as _context_. The context gives the LLM the additional info it needs to generate more accurate, relevant, and up-to-date responses.

To improve the quality of this context, techniques like re-ranking, query expansion, and filtering are commonly used.

#### **Re-ranking**

In essence, re-ranking takes the retrieved documents, analyzes their relevance, and changes their order based on the relevance it perceives. That way, more relevant documents are given higher priority.

#### **Query expansion**

Query expansion takes the original query and adds additional relevant keywords to it. These extra keywords expand the scope of the search and help retrieve relevant documents, which could have otherwise been omitted.

#### **Filtering**

Filtering specifies criteria that the documents must meet in order to include them in the context. This way, only the most relevant documents are selected.

### **LLMs**

LLMs are probably the most well-known component in a RAG approach. In essence, an LLM is just an ML model that has been trained on huge amounts of data, which is what the word _large_ in its name refers to.

LLMs are based on the [transformer architecture](https://www.datacamp.com/tutorial/how-transformers-work), an ML concept that helps with sequential data, like text data. They have countless use cases, some of which are question-answering, summarization, translation, chatbots, virtual assistants, and code generation.

Training an LLM requires curating a huge corpus of textual data. Once enough data is collected, that data is fed to a deep-learning model. With enough data, the deep-learning model starts to understand human language, word meanings, and how sentences are made. LLMs can even be further trained by [fine-tuning or prompt-tuning](https://nexla.com/ai-infrastructure/prompt-tuning-vs-fine-tuning/), which allows the LLM to be better suited for a particular task, such as summarization or translation.

### **Response augmentation and generation**

Once the relevant documents are collected, preprocessed, retrieved, and refined, they're given to the LLM, which already has a lot of information that it was pretrained on. Having both its preexisting knowledge and the context provided by the retrieved documents at its disposal, the LLM generates a response to a user's prompt.

While the LLM can provide an answer even without the help of the retrieved documents, that answer may be outdated or inaccurate. Nevertheless, with the provided context, the LLM can generate relevant, accurate, contextually aware, and up-to-date answers to user prompts.

### **Caching and optimization**

Caching is a great way to further improve and optimize your RAG approach.

With caching, data that’s retrieved often can be stored in a cache, making it easy to retrieve quickly. This also means you don't need to query the data source or the knowledge base every time you need its data.

Caching query results in this way can significantly improve efficiency, reduce retrieval times, and decrease the computational costs. Apart from query results, you can also cache embeddings or re-rankings.

If caching is implemented, any time a user submits a prompt, the RAG system initially checks if the data it needs to generate the response is stored in a cache. If it is, the system retrieves it from the cache and generates a response much faster than usual. If the needed information is not found in the cache, the system retrieves it from the knowledge base instead. The system can also store it in the cache so that it can be used the next time the user submits a similar query.

### **Evaluation and feedback loop**

Even with advanced [RAG tools](https://www.merge.dev/blog/rag-tools) and a flawless setup, there's no guarantee the responses will be free from issues. The system may retrieve irrelevant documents, the quality of responses may be low, or the knowledge bases that the systems rely on may become outdated.

To prevent these or other pitfalls, you need to continuously evaluate the results through metrics, but also by a human.

In addition to evaluating, you also need to integrate a feedback loop and incorporate that feedback back into the system. This is the only way to ensure the system consistently retrieves relevant documents and generates high-quality and accurate responses.

### **Deployment and integration**

After all the previous components have been considered, it's time to deploy and integrate the RAG system into production. The primary step toward deployment is to define the architecture that will support the RAG system. You can choose from options like APIs, microservices, and cloud hosting solutions.

Once that’s decided, the system can actually be deployed—which includes both the retrieval component and the generative model. For the retrieval component, you need a high-performance database, as well as a caching mechanism. Depending on the size of the knowledge base, you can opt for distributed retrieval systems.

Still, deploying the RAG system doesn't mean your job is done. Even after the system is deployed, you need to continuously monitor it and ensure it functions as envisioned.

[Related](https://www.merge.dev/blog/agentic-rag?blog-related=image)

#### [Agentic RAG: definition, benefits, and real-world examples](https://www.merge.dev/blog/agentic-rag?blog-related=image)

[![Agentic RAG: definition, benefits, and real-world examples](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67d8578f0b3a81cb7b7c635a_Blog%20Header%20Brand%20Refresh%20(2).png)](https://www.merge.dev/blog/agentic-rag?blog-related=image)

## **Final thoughts**

A RAG system isn't a simple product or a single off-the-shelf tool. It's a complete, comprehensive system composed of various components. All these components must play their role for the system to be able to initially retrieve information and then generate a response. You need to carefully design each of the components, keeping in mind your needs and the specificities of your use case.

Merge can help you deploy complex architectures like RAG, as it enables your product to access normalized data across hundreds of customers’ applications by simply building to its Unified API.

[![Screenshot of Merge](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/681393c213fec59d03251eb4_AD_4nXemm9Fa0tDuRuJ3YoixOdXHz6DK56Guj9jvmYXX6CsGG8cuSJAf8wNKaXQaLJIx4Kokp8arByhaH_yTCTjjKMlUjauSjBr-L0oIMHBhrHbi4t6TejQs1_XjQGTe893i36hpwyJ5.png)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/681393c213fec59d03251eb4_AD_4nXemm9Fa0tDuRuJ3YoixOdXHz6DK56Guj9jvmYXX6CsGG8cuSJAf8wNKaXQaLJIx4Kokp8arByhaH_yTCTjjKMlUjauSjBr-L0oIMHBhrHbi4t6TejQs1_XjQGTe893i36hpwyJ5.png)

Merge also provides observability features to help your customer-facing teams manage integration issues, enterprise-grade security features to keep your customer data secure, strategic support to help you launch the integrations successfully, and more.

#### Ready to build best-in-class AI features?

Merge lets you access all the customer data you need to power best-in-class RAG pipelines.

[Schedule a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-rag-works)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67b45ba027fc65a2262dc95d_cta-bg.svg)

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Alen Kalac

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

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=34223cd5-f309-48a2-b139-ba47a78a320c&bo=2&sid=67e592303e8d11f0ab932d9a25c2656b&vid=67e63dd03e8d11f09d93b375c8b28f75&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=A%20guide%20on%20how%20retrieval-augmented%20generation%20(RAG)%20works&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-rag-works&r=&lt=596&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=162304)