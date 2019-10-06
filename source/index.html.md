---
title: Pterodactyl API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
#  - php
#  - go
#  - java
#  - javascript


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

The documentation is made for pterodactyl panel v0.7.15.

The API makes use of POST, GET, PATCH and DELETE requests.

If you find any errors throughout this API reference, please [report them](mailto:support@deploys.io).

<!-- Known issues/incompletions are:

 1. ~~Create allocation~~
 2. ~~Create location~~
 3. ~~Edit location~~
 4. ~~Databases Section~~
 5. ~~Anything with the response `{}`~~
 6. ~~`This endpoint does this and that.`~~

**Some parts of this documentation are incomplete.**

If you have a spare moment and have the working request and/or response, please let us know at [support@deploys.io](mailto:support@deploys.io). -->

A special thanks to everyone who has helped contribute!

**Other Pterodactyl API wrappers:**

- [Ptero4J](https://github.com/stanjg/Ptero4J) (Java)
- [Pterodactyl4J](https://github.com/mattmalec/Pterodactyl4J) (Java)
- [crocgodyl](https://github.com/parkervcp/crocgodyl) (Golang)
- [Nodeactyl](https://github.com/Burchard36/Nodeactyl) (Node.js)
- [pterodactyl-sdk](https://github.com/hcgcloud/pterodactyl-sdk) (PHP)
- [Sharpdactyl](https://github.com/KadePcGames/Sharpdactyl) (C#)
- [Pydactyl](https://github.com/iamkubi/pydactyl) (Python)

If you are the developer of any of these wrappers, feel free to [email us](mailto:support@deploys.io) and we can give you access to document your wrapper as a new language tab.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: Bearer meowmeowmeow"
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
```

<!---
```php
# Wrapper language conflict // WrapperA (title is wrapper's name, for example: Ptero4J)
<?php 
echo "owo";
```

```php
# Wrapper language conflict // WrapperB (title is the wrapper's name, for example: Pterodactyl4J)
<?php 
echo "mmm";
```
--->

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

# Request Data Information

```shell
curl "https://pterodactyl.app/api/application/users/<user-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X PATCH \
  -d '
  {
      "external_id": "codeco",
      "username": "codeco",
      "email": "codeco@file.properties",
      "first_name": "Updated",
      "last_name": "User",
      "password": "betterPassword",
      "root_admin": true,
      "language": "en"
  }'
```

All POST & PATCH requests have a table describing the data fields and an example command.

Example:

<!--

Using <code> blocks as | won't get escaped and mess up the table.
Using &#124; for | bc ^

-->

### HTTP Request

`PATCH  https://pterodactyl.app/api/application/users/<user-id>` 

Parameter | Information | Rules
- | - | -
external_id | The external id for the account | <code>sometimes&#124;nullable&#124;string&#124;max:255&#124;unique:users,external_id</code>
username | The username for the account | <code>sometimes&#124;between:1,255&#124;unique:users,username</code>
email | The email address for the account | <code>sometimes&#124;email&#124;unique:users,email</code>
first_name | The user's first name | <code>sometimes&#124;string&#124;between:1,255</code>
last_name | The user's last name | <code>sometimes&#124;string&#124;between:1,255</code>
password | A plain text input of the desired password | <code>sometimes&#124;nullable&#124;string</code>
root_admin | Whether the account is an admin | <code>sometimes&#124;boolean</code>
language | The language for the account | <code>sometimes&#124;string</code> (+ in available languages)

Parameter: Name of the parameter.  
Information: Description of the parameter.  
Rules: Parameter's rules, formated as [Laravel's Validation Rules](https://laravel.com/docs/5.8/validation#available-validation-rules).