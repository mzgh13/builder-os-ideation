---
url: "https://www.merge.dev/blog/managing-long-running-tasks-with-celery-and-kubernetes-or-keeping-your-sanity-during-deploys"
title: "Managing long-running tasks with Celery and Kubernetes (or, keeping your sanity during deploys)"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/managing-long-running-tasks-with-celery-and-kubernetes-or-keeping-your-sanity-during-deploys#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/managing-long-running-tasks-with-celery-and-kubernetes-or-keeping-your-sanity-during-deploys#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/managing-long-running-tasks-with-celery-and-kubernetes-or-keeping-your-sanity-during-deploys#)

Table of contents

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fmanaging-long-running-tasks-with-celery-and-kubernetes-or-keeping-your-sanity-during-deploys)

##### Just for you

No items found.

# Managing long-running tasks with Celery and Kubernetes (or, keeping your sanity during deploys)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c74f43703047123799f_Anthropic_API_key.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd5387ca3e2516664e369a_62eff9710897772d5f67ff9d_lee.webp)

Lee Wang

Software Engineer

@Merge

_Editor's note: This is a series on API-based integrations. Check out Merge if you're looking to add 150+ integrations across HR, ATS, CRM, Accounting, and Project Management platforms with one_ [_unified API_](https://merge.dev/).

‍

Stuck between a rock\* and a hard place\*\*?

\*needing to maintain long-running, customer-critical tasks

\*\*needing to deploy code on Kubernetes clusters that execute those very long-running tasks

As an engineer working on a unified API that handles many, many long-running tasks, I’ve encountered just that very problem. Together, our team has worked out a solution that manages the tension between customer-critical operations and code deployments on Kubernetes clusters. Maybe you’ll find the solution helpful too.

This article assumes you’re at least a little familiar with Celery, Kubernetes, and data-intensive applications. It also acts in conversation with a post from our friends over at [Brex](https://medium.com/brexeng/kubernetes-rolling-update-and-termination-grace-periods-d922c6b84d88) \- so make sure you take a read if you want to fully understand the problem and range of solutions!

Without further ado, let’s get into it.

#### **The Problem**

Let’s break down the problem landscape.

At Merge, our backend services run AWS EKS and use the [Celery framework](https://docs.celeryq.dev/en/stable/getting-started/introduction.html) for scheduling asynchronous work.

Many of our tasks, such as the initial creation of a customer’s account, can take hours to run. Why? As a unified API, we’re dependent on third-party API-specific features, such as rate limits, that inhibit our ability to pull data quickly.

Now, imagine where this run time becomes an issue: at the same time that one of these long-running tasks is operating, we need to deploy code as part of a Kubernetes cluster. The very cluster that is responsible for running those tasks.

It’s a lot like that two-buttons meme.

[![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a3bf48f4b3fec4b8d37a9e_62d7308a2672d64af4434025_Kubernetes%2520Meme.webp)](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a3bf48f4b3fec4b8d37a9e_62d7308a2672d64af4434025_Kubernetes%2520Meme.webp)

_The feeling of the high-wire act of balancing different deployments with Kubernetes_

Boiled down, our team found this problem is due to a combination of **3 factors, all linked to how we restart our servers**:

- The requirements of the [Kubernetes shutdown process](https://cloud.google.com/blog/products/containers-kubernetes/kubernetes-best-practices-terminating-with-grace). This involves: sending SIGTERM to the container, waiting a configured amount of seconds `terminationGracePeriodSeconds` hoping that the container stops itself, then sending SIGKILL to the container, forcing the end of all running processes. [‍](https://docs.celeryq.dev/en/stable/userguide/workers.html#stopping-the-worker)
- [Celery SIGTERM behavior](https://docs.celeryq.dev/en/stable/userguide/workers.html#stopping-the-worker). This is when the worker will stop trying to pull in new tasks while continuing to work on tasks it has already pulled from the Celery broker (which is a global, persistent task queue). **This is known as a “warm shutdown” in Celery lingo.** ‍
- The default terminationGracePeriodSeconds configuration is 30 seconds. While plenty for most tasks, it’s barely enough to run even a single API request depending on the Accounting / ATS / HRIS / Ticketing / CRM platform we are unifying.

While our friends at Brex wanted to keep their dependencies in sync with Elixir/Kafka, we want to keep long-running tasks moving with Python/Celery. Still, the methods we’ve used to solve our problems are largely the same.

(If it's not clear enough - I really recommend reading [Brex’s article about their solution](https://medium.com/brexeng/kubernetes-rolling-update-and-termination-grace-periods-d922c6b84d88)!)

#### **The Fix: Rolling Updates**

Let’s start with what doesn’t work.

A naive approach involves increasing the `terminationGracePeriodSeconds` setting to several minutes. While this would work from a Celery and Kubernetes perspective, it would not play well with our continuous integration scripts which [waited along with Kubernetes for that duration](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#recreate-deployment).

As they say in their docs, “successful removal is awaited before any Pod of the new revision is created.”

Rather than have our CI controlling the entire process, and waiting alongside Kubernetes, we’d rather have Kubernetes be intelligent about its own restarts and let the CI scripts hand off the responsibility to the cluster.

Thankfully, such a capability exists in the `RollingUpdate` [deployment type](https://kubernetes.io/docs/tutorials/kubernetes-basics/update/update-intro/).

See, prior to our current configuration, we had been using the Recreate deployment type. This caused the re-starting behavior that introduced our rock-and-hard-place problem. The magic of `RollingUpdate`, then, is that it crucially lets you configure two values that let Kubernetes handle the rollout on its own:

- **maxSurge:** the percentage above your normal pod count that you can have during the deployment. So if you normally have 10 pods, and configure a `maxSurge` of 20%, you will have up to 12 pods during the deploy. **‍**
- **maxUnavailable:** the percentage of your normal pod count that can be anything OTHER than READY state during the deploy. So for 10 pods, and a `maxUnavailable` of 20%, at least 8 will be READY because the setting stipulates that at most 2 may be non-READY. (The double negative may be confusing, but you can think of it as ~minAvailable if your name is [De Morgan](https://en.wikipedia.org/wiki/De_Morgan%27s_laws)).
- Note that TERMINATING (which is the status that our long-running task pods will have) counts towards the `maxUnavailable` count, meaning that it is the % of our pod count that we want to allow to continue running to celery task completion during the RollingUpdate.

No more sweating over two equally important goals!

With our rolling updates, we can have confidence that long-running tasks have enough time to wrap themselves up, as well as ensure that we can deploy the latest versions of our services to the necessary clusters.

#### **Complications**

Astute link clickers will note that we came to a different conclusion than Brex did. For Brex, the solution was in the `maxUnavailable` setting, which allowed them to guarantee all pods were running and alive, rather than be stuck in a loop of mismatched deployments. It’s worth pointing out that their Elixir libraries do not behave in the same manner as our Celery tasks with a warm shutdown thankfully matching Kubernetes expected behavior on SIGTERM, a fortuitous alignment for Merge.

As Thomas writes in Brex’s article, “Graceful shutdown is hard to implement right, as all the pieces of the infrastructure and the software must be properly configured and implemented in harmony.”

Time will tell if we run into cross-dependency issues for other reasons though! For example, we only do backward-compatible database changes but if there ever was a database migration that was not backward compatible then we’d be in trouble with our non-terminating long-running tasks.

### **On Using Helm (an added bonus)**

Merge also uses [helm](https://helm.sh/) for managing our Kubernetes configurations. While great to work with, I found it strangely difficult to find the documentation for where `RollingUpdate` goes in a chart.

So, here is where both settings are in our chart:

```python
spec:
  replicas: ###
  strategy:
    type: "RollingUpdate"  (formerly Recreate)
    rollingUpdate:
      maxSurge: "## %"
      maxUnavailable: "## %"
  selector:
    matchLabels:
  template:
    metadata:
      ...
    spec:
      ...
      terminationGracePeriodSeconds: ###
  ...
```

### **Want more?**

Up for more Kubernetes and Celery-related fun? Check out [our engineering blog](https://www.merge.dev/blog?content-topic=Engineering#all-blogs) or our [open engineering roles](https://www.merge.dev/careers).

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

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=f735714c-2cea-4b79-a62d-c9396d5398c9&bo=2&sid=355ff3403e8c11f08e225d6a5b978692&vid=356039d03e8c11f0827a7335a35d7ef1&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Managing%20long-running%20tasks%20with%20Celery%20and%20Kubernetes%20(or,%20keeping%20your%20sanity%20during%20deploys)&p=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fmanaging-long-running-tasks-with-celery-and-kubernetes-or-keeping-your-sanity-during-deploys&r=&lt=351&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=734316)