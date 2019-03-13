
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

This endpoint does this and that.

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

This endpoint does this and that.

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

This endpoint does this and that.

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
      "username": "example",
      "email": "example@example.com",
      "first_name": "John",
      "last_name": "Doe",
      "password": "cat"
  }'
```
> The above command returns JSON structured like this:

```json
{
  "object": "user",
  "attributes": {
    "id": 7,
    "external_id": null,
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
    "resource": "https:\/\/pterodactyl.development.deluxenode.com\/api\/application\/users\/7"
  }
}
```

This endpoint does this and that.

Parameter | Information
- | -
username | The username for the accoount
email | The email address for the account
first_name | The user's first name
last_name | The user's last name
password | A plain text input of the desired password

### HTTP Request

`POST  https://pterodactyl.app/api/application/users` 






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
      "username": "codeco",
      "email": "codeco@file.properties",
      "first_name": "Updated",
      "last_name": "User"
  }'
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

This endpoint does this and that.

Parameter | Information
- | -
username | The username for the accoount
email | The email address for the account
first_name | The user's first name
last_name | The user's last name
password | A plain text input of the desired password

### HTTP Request

`PATCH  https://pterodactyl.app/api/application/users/<user-id>` 






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
> The above command returns JSON structured like this:

```json
```

This endpoint does this and that.

### HTTP Request

`DELETE  https://pterodactyl.app/api/application/users/<user-id>`