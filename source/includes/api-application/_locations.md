
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
    },
    {
      "object": "location",
      "attributes": {
        "id": 2,
        "short": "yes",
        "long": "yes test",
        "updated_at": "2018-04-06T02:12:23+00:00",
        "created_at": "2018-04-06T02:12:23+00:00"
      }
    }
  ],
  "meta": {
    "pagination": {
      "total": 2,
      "count": 2,
      "per_page": 50,
      "current_page": 1,
      "total_pages": 1,
      "links": []
    }
  }
}
```

This endpoint retrieves all locations on the panel along with information about them.

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

This endpoint retrieves information for the specified location.

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
    "short": "us.datacenter",
    "long": "US Datacenter"
  }'
```
> The above command returns JSON structured like this:

```json
{
  "object": "location",
    "attributes": {
      "id": 3,
      "short": "us.datacenter",
      "long": "US Datacenter",
      "updated_at": "2019-10-06T16:55:48+00:00",
      "created_at": "2019-10-06T16:55:48+00:00"
    },
    "meta": {
      "resource": "https://pterodactyl.app/api/application/locations/3"
    }
}
```

This endpoint creates a location using the specified information.

### HTTP Request

`POST https://pterodactyl.app/api/application/locations` 

Parameter | Information | Rules
- | - | -
short | The location's short name | <code>required&#124;string&#124;between:1,60&#124;unique:locations,short</code>
long | The location's long name | <code>required&#124;string&#124;between:1,255</code>





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
    "short": "us.ny.datacenter",
    "long": "US NY Datacenter"
  }'
```
> The above command returns JSON structured like this:

```json
{
  "object": "location",
    "attributes": {
      "id": 3,
      "short": "us.ny.datacenter",
      "long": "US NY Datacenter",
      "updated_at": "2019-10-06T16:57:25+00:00",
      "created_at": "2019-10-06T16:55:48+00:00"
    }
}
```

This endpoint edits the specified location using the provided information.

### HTTP Request

`PATCH https://pterodactyl.app/api/application/locations/<location-id>` 

Parameter | Information | Rules
- | - | -
short | The location's short name | <code>required&#124;string&#124;between:1,60&#124;unique:locations,short</code>
long | The location's long name | <code>required&#124;string&#124;between:1,255</code>






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

This endpoint deletes the specified location.

### HTTP Request

`DELETE https://pterodactyl.app/api/application/locations/<location-id>`