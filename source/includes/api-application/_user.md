
# API - Application - User 

<!--
######################################
  ==> GET /api/application/users
######################################
-->
## List users


```shell
curl "https://pterodactyl.app/api/application/users" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```
> The above command returns JSON structured like this:

```json
{
  "object": "list",
  "data": [
    {
      "object": "user",
      "attributes": {
        "id": 1,
        "external_id": null,
        "uuid": "c4022c6c-9bf1-4a23-bff9-519cceb38335",
        "username": "codeco",
        "email": "codeco@file.properties",
        "first_name": "Rihan",
        "last_name": "Arfan",
        "language": "en",
        "root_admin": true,
        "2fa": false,
        "created_at": "2018-03-18T15:15:17+00:00",
        "updated_at": "2018-10-16T21:51:21+00:00"
      }
    },
    {
      "object": "user",
      "attributes": {
        "id": 4,
        "external_id": null,
        "uuid": "f253663c-5a45-43a8-b280-3ea3c752b931",
        "username": "wardledeboss",
        "email": "wardle315@gmail.com",
        "first_name": "Harvey",
        "last_name": "Wardle",
        "language": "en",
        "root_admin": false,
        "2fa": false,
        "created_at": "2018-09-29T17:59:45+00:00",
        "updated_at": "2018-10-02T18:59:03+00:00"
      }
    },
    {
      "object": "user",
      "attributes": {
        "id": 5,
        "external_id": null,
        "uuid": "0d8da9a5-6ccd-4b57-9786-70a97a1a55e7",
        "username": "matthewp",
        "email": "me@matthewp.io",
        "first_name": "Matthew",
        "last_name": "Penner",
        "language": "en",
        "root_admin": true,
        "2fa": false,
        "created_at": "2018-09-29T22:39:05+00:00",
        "updated_at": "2018-09-29T22:39:27+00:00"
      }
    },
    {
      "object": "user",
      "attributes": {
        "id": 6,
        "external_id": null,
        "uuid": "d006fe91-3c64-4b0c-81d1-718af2cc384e",
        "username": "rihan554rnk",
        "email": "rihan554@gmail.com",
        "first_name": "Server",
        "last_name": "Subuser",
        "language": "en",
        "root_admin": false,
        "2fa": false,
        "created_at": "2018-10-02T21:26:18+00:00",
        "updated_at": "2018-10-02T21:26:18+00:00"
      }
    }
  ],
  "meta": {
    "pagination": {
      "total": 4,
      "count": 4,
      "per_page": 50,
      "current_page": 1,
      "total_pages": 1,
      "links": []
    }
  }
}
```

This endpoint retrieves all users along with information about them.

### HTTP Request

`GET https://pterodactyl.app/api/application/users` 






<!--
######################################
  ==> GET /api/application/users/{user}
######################################
-->
## Get user information


```shell
curl "https://pterodactyl.app/api/application/users/<user-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```
> The above command returns JSON structured like this:

```json
{
  "object": "user",
  "attributes": {
    "id": 1,
    "external_id": null,
    "uuid": "c4022c6c-9bf1-4a23-bff9-519cceb38335",
    "username": "codeco",
    "email": "codeco@file.properties",
    "first_name": "Rihan",
    "last_name": "Arfan",
    "language": "en",
    "root_admin": true,
    "2fa": false,
    "created_at": "2018-03-18T15:15:17+00:00",
    "updated_at": "2018-10-16T21:51:21+00:00"
  }
}
```

This endpoint retrieves information for the specified user.

### HTTP Request

`GET https://pterodactyl.app/api/application/users/<user-id>` 






<!--
######################################
  ==> GET /api/application/users/external/{external_id}
######################################
-->
## Get user by external ID


```shell
curl "https://pterodactyl.app/api/application/users/external/<external-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```
> The above command returns JSON structured like this:

```json
{
  "object": "user",
  "attributes": {
    "id": 1,
    "external_id": "1",
    "uuid": "c4022c6c-9bf1-4a23-bff9-519cceb38335",
    "username": "codeco",
    "email": "codeco@file.properties",
    "first_name": "Rihan",
    "last_name": "Arfan",
    "language": "en",
    "root_admin": true,
    "2fa": false,
    "created_at": "2018-03-18T15:15:17+00:00",
    "updated_at": "2018-10-16T21:51:21+00:00"
  }
}
```

This endpoint retrieves information for the specified user with the external id.

### HTTP Request

`GET https://pterodactyl.app/api/application/users/external/<external-id>` 






<!--
######################################
  ==> POST /api/application/users
######################################
-->
## Create user


```shell
curl "https://pterodactyl.app/api/application/users" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST \
  -d '
  {
      "external_id": "example_ext_id",
      "username": "example",
      "email": "example@example.com",
      "first_name": "John",
      "last_name": "Doe",
      "password": "cat",
      "root_admin": false,
      "language": "en"
  }'
```
> The above command returns JSON structured like this:

```json
{
  "object": "user",
  "attributes": {
    "id": 7,
    "external_id": "example_ext_id",
    "uuid": "68b23b39-f172-4cd3-ba4a-ef5761c01374",
    "username": "example",
    "email": "example@example.com",
    "first_name": "John",
    "last_name": "Doe",
    "language": "en",
    "root_admin": false,
    "2fa": false,
    "created_at": "2018-11-20T03:05:23+00:00",
    "updated_at": "2018-11-20T03:05:23+00:00"
  },
  "meta": {
    "resource": "https://pterodactyl.app/api/application/users/7"
  }
}
```

This endpoint creates a new user with the provided information.

### HTTP Request

`POST  https://pterodactyl.app/api/application/users` 

Parameter | Information | Rules
- | - | -
external_id | The external id for the account | <code>sometimes&#124;nullable&#124;string&#124;max:255&#124;unique:users,external_id</code>
username | The username for the account | <code>required&#124;between:1,255&#124;unique:users,username</code>
email | The email address for the account | <code>required&#124;email&#124;unique:users,email</code>
first_name | The user's first name | <code>required&#124;string&#124;between:1,255</code>
last_name | The user's last name | <code>required&#124;string&#124;between:1,255</code>
password | A plain text input of the desired password | <code>sometimes&#124;nullable&#124;string</code>
root_admin | Whether the account is an admin | <code>sometimes&#124;boolean</code>
language | The language for the account | <code>sometimes&#124;string</code> (+ in available languages)





<!--
######################################
  ==> PATCH /api/application/users/{user}
######################################
-->
## Edit user


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
> The above command returns JSON structured like this:

```json
{
  "object": "user",
  "attributes": {
    "id": 1,
    "external_id": "codeco",
    "uuid": "c4022c6c-9bf1-4a23-bff9-519cceb38335",
    "username": "codeco",
    "email": "codeco@file.properties",
    "first_name": "Updated",
    "last_name": "User",
    "language": "en",
    "root_admin": true,
    "2fa": false,
    "created_at": "2018-03-18T15:15:17+00:00",
    "updated_at": "2018-12-17T19:34:37+00:00"
  }
}
```

This endpoint edits the specified user with the provided information.

### HTTP Request

`PATCH  https://pterodactyl.app/api/application/users/<user-id>` 

Parameter | Information | Rules
- | - | -
external_id | The external id for the account | <code>sometimes&#124;nullable&#124;string&#124;max:255&#124;unique:users,external_id</code>
username | The username for the account | <code>required&#124;between:1,255&#124;unique:users,username</code>
email | The email address for the account | <code>required&#124;email&#124;unique:users,email</code>
first_name | The user's first name | <code>required&#124;string&#124;between:1,255</code>
last_name | The user's last name | <code>required&#124;string&#124;between:1,255</code>
password | A plain text input of the desired password | <code>sometimes&#124;nullable&#124;string</code>
root_admin | Whether the account is an admin | <code>sometimes&#124;boolean</code>
language | The language for the account | <code>sometimes&#124;string</code> (+ in available languages)






<!--
######################################
  ==> PATCH /api/application/users/{user}
######################################
-->
## Delete user


```shell
curl "https://pterodactyl.app/api/application/users/<user-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X DELETE
```

This endpoint deletes the specified user.

### HTTP Request

`DELETE  https://pterodactyl.app/api/application/users/<user-id>`