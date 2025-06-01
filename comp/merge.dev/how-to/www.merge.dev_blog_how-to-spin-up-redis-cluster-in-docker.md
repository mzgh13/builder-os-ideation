---
url: "https://www.merge.dev/blog/how-to-spin-up-redis-cluster-in-docker"
title: "How to spin up Redis Cluster in Docker"
---

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/blog/how-to-spin-up-redis-cluster-in-docker#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/blog/how-to-spin-up-redis-cluster-in-docker#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/blog/how-to-spin-up-redis-cluster-in-docker#)

Table of contents

[Configuring Redis Cluster](https://www.merge.dev/blog/how-to-spin-up-redis-cluster-in-docker#configuring-redis-cluster)

###### Add hundreds of integrations to your product through Merge’s Unified API

[Get a demo](https://www.merge.dev/get-in-touch?utm_btn=dr-page-blog%2Fhow-to-spin-up-redis-cluster-in-docker)

##### Just for you

No items found.

# How to spin up Redis Cluster in Docker

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67856c7251ac179ef5aaee50_RAG_examples.webp)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67bb20bbddb103e7c31a2af4_author-1.jpeg)![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64dd5387ca3e2516664e369a_62eff9710897772d5f67ff9d_lee.webp)

Lee Wang

Software Engineer

@Merge

Recently, Merge ran into the need to move to Redis Cluster for a few workloads. A quick primer on the differences:

| Redis Classic | Redis Cluster |
| --- | --- |
| Vertically scaled (i.e. bigger machines) | Horizontal scaling option (i.e. more machines) |
| Single writer, multiple replicas | Multiple writers, multiple replicas |
| Runs all Redis commands | Cannot use multi-key commands |
| Simple Docker local setup | Why you are reading this article |

Redis Cluster takes some getting used to, especially if you need commands such as LPOPRPUSH or others that operate on multiple keys. The reason for this is that cluster-mode moves your data onto multiple “shards” (individual Redis instances in the cluster) but as a result, it cannot guarantee that any two keys are on the same shard, and two different shards cannot share the command if each has one of the keys.

While things like this can be worked around in application logic, something that you probably won’t be able to do without is a way to, how do you say, TEST this setup. Sure, you could run a test suite against your development environment, but that will slow down your developers’ iteration speed if they can’t run this on their laptops.

Your Redis-classic docker-compose section may look like:

```yaml
redis:
 image: redis:6.x.y-alpine
 networks:
   - your-local-network
 ports:
   - "6379:6379"
```

But don’t worry, the cluster-version isn’t THAT much worse especially if you copy a few of our scripts further down!

## Configuring Redis Cluster

Before we begin, I’d just like to shout out this [medium article](https://medium.com/commencis/creating-redis-cluster-using-docker-67f65545796d) for the basics. Any Redis Cluster needs:

- Individual Redis instances
- And a configuration script that tells them about each other
- And what each nodes’ job is (primary vs replica, how many shards there are)

The reason these scripts are better is that this script does not require you to set IP addresses for your Redis nodes. To do that, we leverage the `getent` command to figure out what the Docker network IP address is from within the Docker containers. Let’s start with those individual Redis instances in docker-compose:

```yaml
redis-cluster-node-#:
 image: redis:6.x.y-alpine
 command: redis-server /usr/local/etc/redis/redis.conf
 networks:
   - your-local-network
 ports:
   - "9079:6379"
 volumes:
   - ${PWD}/path/redis_conf_folder:/usr/local/etc/redis
redis-cluster-node-#+1:
 image: redis:6.x.y-alpine
 command: redis-server /usr/local/etc/redis/redis.conf
 networks:
   - your-local-network
 ports:
   - "9080:6379"
 volumes:
   - ${PWD}/path/redis_conf_folder:/usr/local/etc/redis
```

Importantly:

- Allocate as many nodes as you want, be sure to bump the number in the name
- Keep in mind that ports...need unique ports or your local machine will complain about port conflict
- The left half of the volume refers to the folder where you are keeping a redis.conf file

Speaking of redis.conf, it will look like:

```yaml
port 6379
cluster-enabled yes
cluster-config-file nodes.conf
cluster-node-timeout 5000
appendonly yes
```

Which is pretty standard, you won’t need to modify anything there.

Now for the (slightly) complicated part, configuring the cluster and telling these nodes to work together. First off, make a new docker-compose section as follows:

```yaml
redis-cluster-configure:
 image: redis:6.x.y-alpine
 command: /usr/local/etc/redis/redis-cluster-create.sh
 networks:
   - your-local-network
 depends_on:
   - redis-cluster-node-0
   - redis-cluster-node-1
...
 volumes:
   - ${PWD}/path/redis_conf_folder:/usr/local/etc/redis
```

You may notice it follows the same pattern, except that we are running a custom script called `redis-cluster-create.sh`. That file needs to go in your local path/redis-conf-folder (whatever you want to name that) and should be:

```yaml
# wait for the docker-compose depends_on to spin up the redis nodes usually takes this long
sleep 10

node_0_ip=$(getent hosts redis-cluster-node-0 | awk '{ print $1 }')

node_1_ip=$(getent hosts redis-cluster-node-1 | awk '{ print $1 }')

...

redis-cli --cluster create $node_0_ip:6379 $node_1_ip:6379 ... --cluster-replicas 1 --cluster-yes
```

So let’s explain what it does. The sleep is just there to allow you to run “docker-compose up redis-cluster-configure”. When you do that, Docker sees it depends on your individual Redis nodes and spins those up. The 10 second sleep is to allow that to complete since those nodes need to be ready. There’ll be more elegant ways to do this waiting, of course.

What follows is a number of lines (depending on your desired cluster size) that set variables of the IP addresses of your individual Redis nodes. This is the magic part, it allows you to refer to the name you set in the docker-compose of the individual Redis nodes as opposed to hard coding an IP address for them on the local Docker network.

Finally, we run “redis-cli --cluster create …” which takes in those IP addresses (and it must be IP addresses or else we would have passed in the docker-compose node names directly here) which stitches them together into a single cluster.

This all reminds me of the takeaways [from one of our prior articles](https://merge.dev/blog/managing-long-running-tasks-with-celery-and-kubernetes-or-keeping-your-sanity-during-deploys) where the interactions between Celery and Kubernetes resulted in a very specific configuration requirement to get the behavior we desired. Similarly here, we are fulfilling the IP-address requirement using a linux command running inside a dockerized virtual network to get our desired outcome. It just goes to show that in the current era, expertise across a variety of systems is required to get to optimal solutions.

Happy hacking!

{{blog-cta-100+}}

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

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6d0731d2-ccef-4781-b850-b28deb45f46e&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=ab949b1f-9830-4a5a-9e6f-ddeb0e4ed42d&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-spin-up-redis-cluster-in-docker&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=6d0731d2-ccef-4781-b850-b28deb45f46e&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=ab949b1f-9830-4a5a-9e6f-ddeb0e4ed42d&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fblog%2Fhow-to-spin-up-redis-cluster-in-docker&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)