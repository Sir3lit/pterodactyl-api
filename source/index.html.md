---
title: Pterodactyl API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
#  - go

toc_footers:
  - <a href='https://pterodactyl.io'>Website</a>
  - <a href='https://github.com/pterodactyl'>GitHub</a>
  - <a href='https://discord.gg/pterodactyl'>Discord</a>
  - <br>
  - <a href='https://pterodactyl.io/panel/getting_started.html'>Pterodactyl Documentation</a>
  - <br>
  - <a href='https://deploys.io'>Hosted at deploys.io</a>
  - <a href='https://deploys.io'>This documentation is unofficial</a>

includes:
  - api-client/client
  - api-application/user
  - api-application/nodes
  - api-application/locations
  - api-application/servers
  - api-application/nests
  - errors

search: true
---

# Introduction

Welcome to the Pterodactyl API documentation. This documentation is unofficial.

The API makes use of POST, GET, PATCH and DELETE requests.

If you find any errors throughout this API reference, please [report them](mailto:support@deploys.io).

Known issues/incompletions are:

 1. Create allocation
 2. Create location
 3. Edit location
 4. Databases Section
 5. Anything with the response `{}`

**Some parts of this documentation are incomplete.**

If you have a spare moment and have the working request and/or response, please let us know at [support@deploys.io](mailto:support@deploys.io).

A special thanks to everyone who has helped contribute!

**Other Pterodactyl API wrappers:**

- [Ptero4J](https://github.com/stanjg/Ptero4J) (Java)

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: Bearer meowmeowmeow"
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
```

> Make sure to replace `meowmeowmeow` with your API key.

You can obtain an API key from the Account API page within Pterodactyl.

<aside class="warning">
Remember, protect your API key as if it was a password.
</aside>

We expect the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your API key.
</aside>

# Ratelimits

To prevent abuse, the Pterodactyl API has a ratelimit in place.

Up to 60 requests are allowed per minute.

The amount of requests left can be found within the reply header.

Header | Description
---|---
x-ratelimit-limit | The amount of API requests allowed per minute.
x-ratelimit-remaining | The amount of API requests left.