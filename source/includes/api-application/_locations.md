
# API - Application - Locations

<!--
######################################
  ==> GET /api/application/locations
######################################
-->
## List locations


```shell
curl "https://pterodactyl.app/api/application/locations" \
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
      "object": "location",
      "attributes": {
        "id": 1,
        "short": "test",
        "long": "test",
        "updated_at": "2018-04-06T02:12:21+00:00",
        "created_at": "2018-04-06T02:12:21+00:00"
      }
    }
  ],
  "meta": {
    "pagination": {
      "total": 1,
      "count": 1,
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

`GET https://pterodactyl.app/api/application/locations` 






<!--
######################################
  ==> GET /api/application/locations/{location}
######################################
-->
## Get location information


```shell
curl "https://pterodactyl.app/api/application/locations/<location-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```
> The above command returns JSON structured like this:

```json
{
  "object": "location",
  "attributes": {
    "id": 1,
    "short": "test",
    "long": "test",
    "updated_at": "2018-04-06T02:12:21+00:00",
    "created_at": "2018-04-06T02:12:21+00:00"
  }
}
```

This endpoint does this and that.

### HTTP Request

`GET https://pterodactyl.app/api/application/locations/<location-id>` 






<!--
######################################
  ==> POST /api/application/locations
######################################
-->
## Create location


```shell
curl "https://pterodactyl.app/api/application/locations" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST \
  -d '{
    "shortcode": "US",
    "description": "Datacenter"
  }'
```
> The above command returns JSON structured like this:

```json
{}
```

This endpoint does this and that.

### HTTP Request

`POST https://pterodactyl.app/api/application/locations` 






<!--
######################################
  ==> PATCH /api/application/locations/{location}
######################################
-->
## Edit location


```shell
curl "https://pterodactyl.app/api/application/locations/<location-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X PATCH \
  -d '{
    "shortcode": "US",
    "description": "Datacenter"
  }'
```
> The above command returns JSON structured like this:

```json
{}
```

This endpoint does this and that.

### HTTP Request

`PATCH https://pterodactyl.app/api/application/locations/<location-id>` 






<!--
######################################
  ==> DELETE /api/application/locations/{location}
######################################
-->
## Delete location


```shell
curl "https://pterodactyl.app/api/application/locations/<location-id>" \
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

`DELETE https://pterodactyl.app/api/application/locations/<location-id>`