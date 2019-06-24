
# API - Application - Servers

<!--
######################################
  ==> GET /api/application/servers
######################################
-->
## Get all servers


```shell
curl "https://pterodactyl.app/api/application/servers" \
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
      "object": "server",
      "attributes": {
        "id": 2,
        "external_id": null,
        "uuid": "47a7052b-f07e-4845-989d-e876e30960f4",
        "identifier": "47a7052b",
        "name": "Eat Cows",
        "description": "",
        "suspended": false,
        "limits": {
          "memory": 2048,
          "swap": -1,
          "disk": 10000,
          "io": 500,
          "cpu": 300
        },
        "feature_limits": {
          "databases": 10,
          "allocations": 0
        },
        "user": 1,
        "node": 2,
        "allocation": 3,
        "nest": 1,
        "egg": 4,
        "pack": null,
        "container": {
          "startup_command": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
          "image": "quay.io\/pterodactyl\/core:java",
          "installed": true,
          "environment": {
            "SERVER_JARFILE": "server.jar",
            "VANILLA_VERSION": "latest",
            "STARTUP": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
            "P_SERVER_LOCATION": "test",
            "P_SERVER_UUID": "47a7052b-f07e-4845-989d-e876e30960f4"
          }
        },
        "updated_at": "2018-11-20T14:35:00+00:00",
        "created_at": "2018-09-29T22:50:16+00:00"
      }
    },
    {
      "object": "server",
      "attributes": {
        "id": 6,
        "external_id": null,
        "uuid": "6d1567c5-08d4-4ecb-8d5d-0ce1ba6b0b99",
        "identifier": "6d1567c5",
        "name": "Wow",
        "description": "t",
        "suspended": false,
        "limits": {
          "memory": 0,
          "swap": -1,
          "disk": 5000,
          "io": 500,
          "cpu": 200
        },
        "feature_limits": {
          "databases": 0,
          "allocations": 0
        },
        "user": 5,
        "node": 2,
        "allocation": 4,
        "nest": 1,
        "egg": 15,
        "pack": null,
        "container": {
          "startup_command": ".\/parkertron",
          "image": "quay.io\/parkervcp\/pterodactyl-images:parkertron",
          "installed": true,
          "environment": {
            "STARTUP": ".\/parkertron",
            "P_SERVER_LOCATION": "test",
            "P_SERVER_UUID": "6d1567c5-08d4-4ecb-8d5d-0ce1ba6b0b99"
          }
        },
        "updated_at": "2018-11-10T19:52:13+00:00",
        "created_at": "2018-11-10T19:51:23+00:00"
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

This endpoint does this and that.

### HTTP Request

`GET https://pterodactyl.app/api/application/servers` 






<!--
######################################
  ==> GET /api/application/servers/{server}
######################################
-->
## Get server information


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```
> The above command returns JSON structured like this:

```json
{
  "object": "server",
  "attributes": {
    "id": 2,
    "external_id": null,
    "uuid": "47a7052b-f07e-4845-989d-e876e30960f4",
    "identifier": "47a7052b",
    "name": "Survival",
    "description": "gsk;ljgkj;hgdakl;gha",
    "suspended": false,
    "limits": {
      "memory": 2048,
      "swap": -1,
      "disk": 10000,
      "io": 500,
      "cpu": 300
    },
    "feature_limits": {
      "databases": 10,
      "allocations": 0
    },
    "user": 1,
    "node": 2,
    "allocation": 3,
    "nest": 1,
    "egg": 4,
    "pack": null,
    "container": {
      "startup_command": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
      "image": "quay.io\/pterodactyl\/core:java",
      "installed": true,
      "environment": {
        "SERVER_JARFILE": "server.jar",
        "VANILLA_VERSION": "latest",
        "STARTUP": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
        "P_SERVER_LOCATION": "test",
        "P_SERVER_UUID": "47a7052b-f07e-4845-989d-e876e30960f4"
      }
    },
    "updated_at": "2018-11-20T02:52:37+00:00",
    "created_at": "2018-09-29T22:50:16+00:00"
  }
}
```

This endpoint does this and that.

### HTTP Request

`GET https://pterodactyl.app/api/application/servers/<internal-id>` 






<!--
######################################
  ==> GET /api/application/servers/external/{external-id}
######################################
-->
## Get server by external ID


```shell
curl "https://pterodactyl.app/api/application/servers/external/<external-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```
> The above command returns JSON structured like this:

```json
{
  "object": "server",
  "attributes": {
    "id": 7,
    "external_id": "99",
    "uuid": "78165af0-4835-405f-b281-07e961bfd0ad",
    "identifier": "78165af0",
    "name": "Eat Cows",
    "description": "",
    "suspended": false,
    "limits": {
      "memory": 1024,
      "swap": 0,
      "disk": 1000,
      "io": 500,
      "cpu": 0
    },
    "feature_limits": {
      "databases": 0,
      "allocations": 0
    },
    "user": 1,
    "node": 2,
    "allocation": 9,
    "nest": 1,
    "egg": 4,
    "pack": null,
    "container": {
      "startup_command": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
      "image": "quay.io\/pterodactyl\/core:java",
      "installed": true,
      "environment": {
        "SERVER_JARFILE": "server.jar",
        "VANILLA_VERSION": "latest",
        "STARTUP": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
        "P_SERVER_LOCATION": "test",
        "P_SERVER_UUID": "78165af0-4835-405f-b281-07e961bfd0ad"
      }
    },
    "updated_at": "2018-12-17T20:00:16+00:00",
    "created_at": "2018-12-11T21:56:00+00:00"
  }
}
```

This endpoint does this and that.

### HTTP Request

`GET https://pterodactyl.app/api/application/servers/external/<external-id>` 






<!--
######################################
  ==> PATCH /api/application/servers/{server}/details
######################################
-->
## Update server details


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/details" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X PATCH \
  -d '{
    "name": "Eat Cows",
    "user": "1"
  }'
```
> The above command returns JSON structured like this:

```json
{
  "object": "server",
  "attributes": {
    "id": 7,
    "external_id": null,
    "uuid": "78165af0-4835-405f-b281-07e961bfd0ad",
    "identifier": "78165af0",
    "name": "Eat Cows",
    "description": "",
    "suspended": false,
    "limits": {
      "memory": 1024,
      "swap": 0,
      "disk": 1000,
      "io": 500,
      "cpu": 0
    },
    "feature_limits": {
      "databases": 0,
      "allocations": 0
    },
    "user": 1,
    "node": 2,
    "allocation": 9,
    "nest": 1,
    "egg": 4,
    "pack": null,
    "container": {
      "startup_command": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
      "image": "quay.io\/pterodactyl\/core:java",
      "installed": true,
      "environment": {
        "SERVER_JARFILE": "server.jar",
        "VANILLA_VERSION": "latest",
        "STARTUP": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
        "P_SERVER_LOCATION": "test",
        "P_SERVER_UUID": "78165af0-4835-405f-b281-07e961bfd0ad"
      }
    },
    "updated_at": "2018-12-17T20:02:12+00:00",
    "created_at": "2018-12-11T21:56:00+00:00"
  }
}
```

This endpoint does this and that.

### HTTP Request

`PATCH https://pterodactyl.app/api/application/servers/<internal-id>/details` 






<!--
######################################
  ==> PATCH /api/application/servers/{server}/build
######################################
-->
## Update server build configuration


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/build" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X PATCH \
  -d '{
    "allocation": "9",
    "memory": "2048",
    "swap": "-1",
    "io": "500",
    "cpu": "300",
    "disk": "10000",
    "feature_limits": {
      "databases": 10,
      "allocations": 10
    }
  }
```
> The above command returns JSON structured like this:

```json
{
  "object": "server",
  "attributes": {
    "id": 7,
    "external_id": "1510",
    "uuid": "78165af0-4835-405f-b281-07e961bfd0ad",
    "identifier": "78165af0",
    "name": "Eat Cows",
    "description": "",
    "suspended": false,
    "limits": {
      "memory": 2048,
      "swap": -1,
      "disk": 10000,
      "io": 500,
      "cpu": 300
    },
    "feature_limits": {
      "databases": 10,
      "allocations": 10
    },
    "user": 1,
    "node": 2,
    "allocation": 9,
    "nest": 1,
    "egg": 4,
    "pack": null,
    "container": {
      "startup_command": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
      "image": "quay.io\/pterodactyl\/core:java",
      "installed": true,
      "environment": {
        "SERVER_JARFILE": "server.jar",
        "VANILLA_VERSION": "latest",
        "STARTUP": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
        "P_SERVER_LOCATION": "test",
        "P_SERVER_UUID": "78165af0-4835-405f-b281-07e961bfd0ad"
      }
    },
    "updated_at": "2018-12-26T16:33:27+00:00",
    "created_at": "2018-12-11T21:56:00+00:00"
  }
}
```

This endpoint does this and that.

### HTTP Request

`PATCH https://pterodactyl.app/api/application/servers/<internal-id>/build` 






<!--
######################################
  ==> PATCH /api/application/servers/{server}/startup
######################################
-->
## Update server startup parameters


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/startup" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X PATCH \
  -d '{
    "startup": "java -Xms128M -Xmx1024M -jar paper.jar",
    "environment": [
      "SERVER_JARFILE",
      "DL_VERSION"
    ],
    "egg": "1",
    "image": "quay.io/pterodactyl/core:java",
    "skip_scripts": false
  }
```
> The above command returns JSON structured like this:

```json
{}
```

This endpoint does this and that.

### HTTP Request

`PATCH https://pterodactyl.app/api/application/servers/<internal-id>/startup` 






<!--
######################################
  ==> POST /api/application/servers
######################################
-->
## Create server


```shell
curl "https://pterodactyl.app/api/application/servers" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST \
  -d '{
  	"name": "Test",
  	"user": 1,
  	"nest": 5,
  	"egg": 15,
  	"docker_image": "quay.io/pterodactyl/core:java-glibc",
  	"startup": "java -Xms128M -Xmx 1024M -jar server.jar",
  	"limits": {
  		"memory": 512,
  		"swap": 0,
  		"disk": 1024,
  		"io": 500,
  		"cpu": 100
  	},
  	"feature_limits": {
  		"databases": 1,
  		"allocations": 2
  	},
  	"environment": {
  		"DL_VERSION": "1.12.2"
  	},
  	"deploy": {
  		"locations": [1],
  		"dedicated_ip": false,
  		"port_range": []
  	},
  	"start_on_completion": true
  }'
```
> The above command returns JSON structured like this:

```json
{
  "object": "server",
  "attributes": {
    "id": 53,
    "external_id": null,
    "uuid": "d7bcc254-e218-4522-a7fe-9d2d562ad790",
    "identifier": "d7bcc254",
    "name": "Test",
    "description": "",
    "suspended": false,
    "limits": {
      "memory": 512,
      "swap": 0,
      "disk": 1024,
      "io": 500,
      "cpu": 100
    },
    "feature_limits": {
      "databases": 1,
      "allocations": 2
    },
    "user": 1,
    "node": 1,
    "allocation": 28,
    "nest": 5,
    "egg": 15,
    "pack": null,
    "container": {
      "startup_command": "java -Xms128M -Xmx 1024M -jar server.jar",
      "image": "quay.io\/pterodactyl\/core:java-glibc",
      "installed": false,
      "environment": {
        "DL_VERSION": "1.12.2",
        "STARTUP": "java -Xms128M -Xmx 1024M -jar server.jar",
        "P_SERVER_LOCATION": "fr.sys",
        "P_SERVER_UUID": "d7bcc254-e218-4522-a7fe-9d2d562ad790"
      }
    },
    "updated_at": "2019-02-23T11:25:35+00:00",
    "created_at": "2019-02-23T11:25:35+00:00"
  }
}
```

This endpoint will create a server based on the given json object. 

<aside class="notice">
Please note that every environment variable from the egg must be set.
</aside>


### HTTP Request

`POST https://pterodactyl.app/api/application/servers` 






<!--
######################################
  ==> POST /api/application/servers/{server}/suspend
######################################
-->
## Suspend specific server


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/suspend" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST 
```
> The above command returns JSON structured like this:

```json

```

This endpoint does this and that.

### HTTP Request

`POST https://pterodactyl.app/api/application/servers/<internal-id>/suspend` 






<!--
######################################
  ==> POST /api/application/servers/{server}/unsuspend
######################################
-->
## Unsuspend specific server


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/unsuspend" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST 
```
> The above command returns JSON structured like this:

```json

```

This endpoint does this and that.

### HTTP Request

`POST https://pterodactyl.app/api/application/servers/<internal-id>/unsuspend` 






<!--
######################################
  ==> POST /api/application/servers/{server}/reinstall
######################################
-->
## Reinstall specific server


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/reinstall" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST 
```
> The above command returns JSON structured like this:

```json

```

This endpoint does this and that.

### HTTP Request

`POST https://pterodactyl.app/api/application/servers/<internal-id>/reinstall` 






<!--
######################################
  ==> POST /api/application/servers/{server}/rebuild
######################################
-->
## Rebuild specific server


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/rebuild" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST 
```
> The above command returns JSON structured like this:

```json

```

This endpoint does this and that.

### HTTP Request

`POST https://pterodactyl.app/api/application/servers/<internal-id>/rebuild` 






<!--
######################################
  ==> DELETE /api/application/servers/{server}
######################################
-->
## Delete server


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>" \
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

`DELETE https://pterodactyl.app/api/application/servers/<internal-id>` 






<!--
######################################
  ==> DELETE /api/application/servers/{server}/{force?}
######################################
-->
## Forcefully delete server


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/force" \
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

`DELETE https://pterodactyl.app/api/application/servers/<internal-id>/force` 






<!--
######################################
  ==> GET /api/application/servers/{server}/databases
######################################
-->
## Get all a databases from a server


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/databases" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```
> The above command returns JSON structured like this:

```json
{}
```

This endpoint does this and that.

### HTTP Request

`GET https://pterodactyl.app/api/application/servers/<internal-id>/databases` 






<!--
######################################
  ==> GET /api/application/servers/{server}/databases/{database}
######################################
-->
## List specific database from a server


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/databases/<database-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```
> The above command returns JSON structured like this:

```json
{}
```

This endpoint does this and that.

### HTTP Request

`GET https://pterodactyl.app/api/application/servers/<internal-id>/databases/<database-id>` 






<!--
######################################
  ==> POST /api/application/servers/{server}/databases
######################################
-->
## Create database for a server


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/databases" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST 
```
> The above command returns JSON structured like this:

```json
{}
```

This endpoint does this and that.

### HTTP Request

`POST https://pterodactyl.app/api/application/servers/<internal-id>/databases` 






<!--
######################################
  ==> POST /api/application/servers/{server}/databases/{database}
######################################
-->
## Reset specific database password


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/databases/<database-id>/reset-password" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST 
```
> The above command returns JSON structured like this:

```json
{}
```

This endpoint does this and that.

### HTTP Request

`POST https://pterodactyl.app/api/application/servers/<internal-id>/databases/<database-id>/reset-password` 






<!--
######################################
  ==> GET /api/application/servers/{server}/databases/{database}
######################################
-->
## Delete database


```shell
curl "https://pterodactyl.app/api/application/servers/<internal-id>/databases/<database-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X DELETE 
```
> The above command returns JSON structured like this:

```json
{}
```

This endpoint does this and that.

### HTTP Request

`DELETE https://pterodactyl.app/api/application/servers/<internal-id>/databases/<database-id>`