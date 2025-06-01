---
url: "https://www.merge.dev/blog/50-years-of-virtualization-shows-us-whats-coming-next"
title: "50 years of virtualization shows us what’s coming next"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/50-years-of-virtualization-shows-us-whats-coming-next#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/50-years-of-virtualization-shows-us-whats-coming-next#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/50-years-of-virtualization-shows-us-whats-coming-next#)

Table of contents

[Virtualization 0: The InterNetwork](https://www.merge.dev/blog/50-years-of-virtualization-shows-us-whats-coming-next#virtualization-0-the-internetwork)

[Virtualization 1: I am Chroot?](https://www.merge.dev/blog/50-years-of-virtualization-shows-us-whats-coming-next#virtualization-1-i-am-chroot)

[Virtualization 2: Write Once Run Anywhere](https://www.merge.dev/blog/50-years-of-virtualization-shows-us-whats-coming-next#virtualization-2-write-once-run-anywhere)

[Virtualization 3: Sadly Nothing Rhymes with Containerization](https://www.merge.dev/blog/50-years-of-virtualization-shows-us-whats-coming-next#virtualization-3-sadly-nothing-rhymes-with-containerization)

[SaaS, APIs, and Easier Problems](https://www.merge.dev/blog/50-years-of-virtualization-shows-us-whats-coming-next#saas-apis-and-easier-problems)

[Unified APIs Will Virtualize SaaS](https://www.merge.dev/blog/50-years-of-virtualization-shows-us-whats-coming-next#unified-apis-will-virtualize-saas)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2F50-years-of-virtualization-shows-us-whats-coming-next)

##### Just for you

No items found.

# 50 years of virtualization shows us what’s coming next

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856cad22f3719980bd4daf_Unified_APIs_Are_the_Next_Wave_of_Virtualization.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd5387ca3e2516664e369a_62eff9710897772d5f67ff9d_lee.webp)

Lee Wang

Software Engineer

@Merge

There have been uncountably many memes that describe the evolution of the modern tech industry:

- “The Internet is a series of tubes”
- It’s like Uber, but for half-filled water bottles!
- Old man yells at cloud
- And so on…

But virtualization is such a persistent and long-term trend that spans so many layers of the modern tech stack–from networking to operating systems all the way up to programming languages–that it’s worth considering them all in order to divine the future. Dear reader, if you’re willing to read a few dozen words about the past 50 years of computing, I think you will agree.

## Virtualization 0: The InterNetwork

In the 1960s and 1970s, the United States Government commissioned ARPANET to connect the computers of several research universities. These computers communicated using TCP/IP, the second half of which stands for Internet Protocol.

This protocol allowed the sending of data from one network to another, no matter what the communication of each network was. This was especially relevant during the [Protocol Wars](https://en.wikipedia.org/wiki/Protocol_Wars), where different nerds had different opinions on what was the most efficient way for one computer to talk to another. No matter what Harvard’s network administrators decided, it was possible to translate that to Internet Protocol and send that over to Yale’s network. It may be playing with words (but probably not by much) to say that the early internet was a virtual network of networks. Since those days, networks have become more standardized and run TCP/IP natively, but that only happened because it was the most flexible way of unifying disparate network architectures at the beginning.

## Virtualization 1: I am Chroot?

In the 1960s, computers were expensive, took up entire office floors, and used more electricity than an entire suburban home. Given how costly it was to have one around, idle time was something to avoid so having multiple users share a computer was a great way to amortize the costs. [Wikipedia lists IBM](https://en.wikipedia.org/wiki/Timeline_of_virtualization_development) as the first to implement such a sharing system and by 1979, Unix introduced chroot.

Chroot is a Unix (and thus Linux) command that allowed a program to run as if some folder was the root of the entire machine. This was a great way to make sure your pal Joe’s program did not overwrite a file in another folder that belonged to Ted’s program. This modest goal eventually gave way to virtualizing other operating system resources.

## Virtualization 2: Write Once Run Anywhere

Most people have heard of Java as a programming language, but fewer people have heard of the JVM. The Java Virtual Machine is a set of fake, or virtual, CPU instructions for a CPU that does not exist. This would not sound very useful except that actual physical CPUs also have what is known as an instruction set, consisting of things like “add the value at memory address 1 with the value at memory address 2”. Prior to Java, each program written in C, Fortran, or C++ would have to be translated or “compiled” into the instructions for a given physical CPU’s instruction set, sometimes resulting in bugs that were specific to that CPU.

By adding the JVM on top, suddenly programmers did not have to worry about “compiling” or translating their programming language for a given physical CPU, and instead let the makers of Java and the hardware companies hash that out among themselves for how to translate JVM instructions into CPU instruction set x/y/z. Similar to how the Internet virtualized networks, the JVM virtualized CPUs and became the dominant programming language for an entire generation of software companies.

## Virtualization 3: Sadly Nothing Rhymes with Containerization

Building off of the strength of chroot and the early virtual machines (which were slightly different than the JVM), we saw docker and the rise of containerization in the 2010s. A container is a virtual operating system running on your real operating system.

This popular and now ubiquitous tool was a way to not only specify which folder was the root folder of a program, but also much much more. To give a sense of how “turtles all the way down” this is, you can create and run a docker container that:

1. Runs a Java program.
2. Runs on JVM at version 12 (despite JVM version 8 being what is installed on your actual computer).
3. Sees the value of the “STAGE” environment variable as “PRODUCTION” no matter what that value is on your actual operating system.
4. Has access to /joes-folder/ but nothing else.
5. And can only talk to the network on TCP/IP port 4078.

## SaaS, APIs, and Easier Problems

The above virtualization technologies are all relatively fundamental. That is, they all concern topics that are close to the hardware of servers or networks. Whether it be the protocol that dictates how a fiber optic cable transfers Internet data or what the Java program tells the CPU to actually do with the bits, these are far from the concerns of a standard software engineer writing a widget for company X.

But, because of the standardization and ease of use brought about by prior generations of virtualization, Software-as-a-Service has come to dominate the tech industry where companies sell licenses to software they run on behalf of their customers running on (often) virtual servers rented from cloud providers that the end customer interacts with via browsers over the Internet. In other words, we are in an era where APIs are critical because systems can so easily share data over the network, so no one is incentivized to run their own physical boxes.

There are still problems, though, because one year you may be pulling down API data from Zenefits while the next you may need to consume data from Workday. These APIs have different formats, and sometimes even different relationships between very similar-sounding concepts. What is a simple “job title” property in one system may be an entire “employment” object in another.

## Unified APIs Will Virtualize SaaS

Let’s consider a more concrete example. If system A sends employee data as:

```python
{
    “Name”: “Tux Penguin”
    “EmployeeId”: 88
}

```

But system B responded with:

```python

<soap:envelope xmlns=”contrived example”>
    <employee>
        <firstname>Tux</firstname>
        <lastname>Penguin</lastname>
        <number>AA52</number>
    </employee>
</soap>

```

Sure, both of these pieces of data will come back to your server as text through all these virtual tubes, but you poor reader are on the hook to:

1. Notice that system A is JSON format
2. Split the first name and last name on the space (but what if there’s a middle name or a Jr/Sr suffix?)
3. Notice system B is some SOAP format cousin that I made up just now
4. Separates out the first and last name for you but
5. Why is the employee’s id labeled as “number” but has “AA” in it?

In other words, in a world where there are dozens of HR platforms that have your customers data on them which you would love to ingest in order to power your Uber-for-water-bottles SaaS company, you have to painstakingly pluck from each platform the data relevant to you in some weird format that is unique to them. And if you give up three other roadmap items that are actual differentiating features in order to onboard a big customer? That’s just the cost of integrating.

Well, dear reader, just as the Internet Protocol lets networks talk to each other, just as chroot lets different programs share an operating system, just as Java lets programmers not worry about Intel or Arm, and just as docker/kubernetes lets services run on whatever fake operating system they need, so too will unified APIs let companies talk to each other in a more efficient manner.

For example, Merge’s [Unifed API](https://merge.dev/blog/what-is-a-unified-api) standardizes the properties of both systems into this format using the Employee model:

```python

{
 "id": "0958cbc6-6040-430a-848e-aafacbadf4ae",
 "remote_id": "19202938",
 "employee_number": "AA52",
 "first_name": "Tux",
 "last_name": "Penguin",
…

```

And it’s Merge’s sole focus to figure out the best mapping. Just like prior virtualization technologies, the general need for networking/CPU-instructions/Operating-System-Configuration rests with one party, freeing you up to do what makes your company actually unique and valuable.

“It was the same process, go talk to their team, figure out their API. It was taking a lot of time. And then before we knew it, there was a laundry list of HR integrations being requested for our prospects and customers.”

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Name

Position

Position

![](https://cdn.prod.website-files.com/plugins/Basic/assets/placeholder.60f9b1840c.svg)

Lee Wang

Software Engineer

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