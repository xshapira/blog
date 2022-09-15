---
date: 2022-09-20
categories:
- HTTPX
- HTTP
links:
    - https://www.python-httpx.org/
readtime: "?"
---

# Should I use HTTPX?

Let's talk a bit about [**HTTPX**](https://www.python-httpx.org/). :nerd:

If you are working with modern Python technologies like [**FastAPI**](https://fastapi.tiangolo.com/), you might have heard about **HTTPX**.
It is a modern HTTP client for Python 3.7+ that provides sync and async APIs, and it is a great alternative to
[**requests**](https://requests.readthedocs.io/en/latest/).

**HTTPX** was created by [Tom Christie](https://www.tomchristie.com/), the same person who created [**MkDocs**](https://www.mkdocs.org/),
[**Django-REST-Framework**](https://www.django-rest-framework.org/), [**Uvicorn**](https://www.uvicorn.org/) and
[**Starlette**](https://www.starlette.io/). Nowadays, Tom is mainly focused on **HTTPX**.

## HTTPX Features

Before writing this blog post I asked Tom what I couldn't miss on this blog post, and the first message he sent was:

> The CLI. Timeout behaviour.

So, let's start with those two things.

### The CLI

**HTTPX** provides a CLI that can be used to make HTTP requests.

WRITE MORE HERE

### Timeout behavior

When using **requests**, there's no default `timeout` value. In other words, if you don't set the `timeout`, the request can hang forever.
This is actually a known issue, and you can read more about it [here](https://github.com/psf/requests/issues/3070).

There are solutions to set a default timeout value, but they involve a lot of complexity. For example, [Adam Johnson](https://adamj.eu/) proposes
to use [patchy](https://github.com/adamchainz/patchy) to patch the `requests` module on his article about ["How to Patch Requests to Have a Default Timeout"](https://adamj.eu/tech/2022/06/23/how-to-patch-requests-to-have-a-default-timeout/).

**HTTPX** is careful to [enforce timeouts everywhere](https://www.python-httpx.org/advanced/#timeout-configuration) by default.
There are 4 different types of timeout that may occur:

* `connect`: The maximum amount of time to establish a connection to the server.
* `read`: The maximum amount of time to read the first byte of the response.
* `write`: The maximum amount of time to send the first byte of request data to the server.
* `pool`: The maximum amount of time to wait for acquiring a connection from the the connection pool.

All of the above default to 5 seconds. You can read more about it, and how to configure them on the
[**HTTPX** documentation](https://www.python-httpx.org/advanced/#fine-tuning-the-configuration).

## Why should I NOT use HTTPX?

There are some arguments to not use **HTTPX**. Let's talk about them.

WRITE SOMETHING ABOUT https://www.confessionsofadataguy.com/httpx-vs-requests-in-python-performance-and-other-musings/

### HTTPX is still new

**HTTPX** is still new. It was released in 2019, and it is still in version 0.23.0. It is not even in version 1.0.0 yet.

But... Does the version number really matter? I don't think so.

### Benchmark
