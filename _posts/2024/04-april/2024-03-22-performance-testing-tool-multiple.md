---
title: "New performance testing tool Multiple"
header:
  # image: /assets/images/2024/04/02/multiple.jpg
  teaser: /assets/images/co-author/Dennis_Nyawiara.jpeg
  # caption: "Photo credit: Unplash"
permalink: "/post/performance-testing-tool-multiple.html"
search : false
date: 2024-04-01
authors: 
  - Millan Kaul
categories:
  - blog
  - tools
tags:
  - performance testing
  - Shift Left
  - Test automation
---

<p>
 Written by -
{% if page.authors == nil or page.authors.size == 0 %}
   {{ page.author }}
{% else %}
    {% assign result = "" %}
    {% for author in page.authors %}
        {% if author != nil and author != "" %}
            {% if forloop.first %}
                {% assign result = author %}
            {% elsif forloop.last %}
                {% assign result = result | append: " and " | append: author %}
            {% else %}
                {% assign result = result | append: ", " | append: author %}
            {% endif %}
        {% endif %}
    {% endfor %}
    {% if result != "" %}
        <strong>{{ result }}</strong>
    {% endif %}
{% endif %}
</p>

<hr style="border: none; height:2px; background-color: #A9F1E4; position: relative;">

Multiple is a developer-centric load test platform that can test anything across your stack. More on [multiple.dev](https://www.multiple.dev/).

History : Multiple took off [Multiple's Signup is Live!](https://www.multiple.dev/blog/multiple-is-live) on December 7, 2023 and started with a problem statement to solve three challenges with existing tools, on the lines of :

1. Limited scripting capabilities. XML or GUI-based scripting can only test basic scenarios...

2. Cannot use existing libraries or code. Instead of forcing you to learn a new system and rewrite code, Multiple leverages the JavaScript and NPM ecosystem.... << my personal favourite :heart: 

3. Tedious infrastructure management....

## Introduction

Fron [official web](https://docs.multiple.dev/introduction) 
> Multiple is a load test platform built for developers. With a few lines of JavaScript, you can create and run scalable load tests, observe the results in real-time, and easily share them with your team.


## Why use Multiple?

- Write load tests with Javascript and NPM packages; no proprietary tools or config files
- Works with almost any service, database, and protocol out of the box, including Kafka, EC2, MongoDB, Redis, and gRPC
- Managed infrastructure lets you spin up large load tests in seconds without setting up and tearing down your own cloud resources
- It’s easy to share tests and test results with your team


As I mentioned earlier my :heart: works with custom NPM packages.

like

```javascript
// faker for generating synthetic data
import { faker } from '@faker-js/faker';

class LotsOfChatMxTestSpec {
  npmDeps = {
    '@faker-js/faker': '7.6.0',
  };

  async vuInit(ctx) {
    ....
    // Log in as a user and get a JWT
    const res = await ctx.axios.post('login', {
      email: `user@email.com`,
      password: 'password',
    });
  }

  async vuLoop(ctx) {
    // Send a POST request to the chat endpoint with a random message
    await ctx.axios.post('chat', {
      // Generate synthetic data with faker
      message: faker.lorem.paragraph(),
    });

    // Send a GET request to the chat endpoint
    await ctx.axios.get('chat');
  }

}

```

# ++

It supports `dotenv` **Environment Variables** 

```bash
# Base URL for the API
API_BASE_URL=https://example-api.multiple.dev
```


## Let's compare it with similar tool k6
...

## Verdict

As of April 2024..



<br>
<br>

<hr style="border: none; height:1px; background-color: #0F4CCC; position: relative;">

Want to learn more❓
<br> 
Follow [Quality With Millan](https://www.linkedin.com/company/quality-with-millan) or <a href="https://www.linkedin.com/shareArticle?url=https://qualitywithmillan.github.io{{ page.url }}&title=I+came+through+this+awesome+blogs+on+%0A%23QualityWithMillan" title="I came through this awesome blogs on #QualityWithMillan" target="_blank">Share it on LinkedIn</a>

<hr style="border: none; height:1px; background-color: #0F4CCC; position: relative;">

