
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
          "image": "quay.io/pterodactyl/core:java",
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
          "startup_command": "./parkertron",
          "image": "quay.io/parkervcp/pterodactyl-images:parkertron",
          "installed": true,
          "environment": {
            "STARTUP": "./parkertron",
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

This endpoint retrieves all servers along with information about them.

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
      "image": "quay.io/pterodactyl/core:java",
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

This endpoint retrieves information for the specified server.

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
    "external_id": "cow_eater",
    "uuid": "78165af0-4835-405f-b281-07e961bfd0ad",
    "identifier": "78165af0",
    "name": "Eat Cows",
    "description": "ok....",
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
      "image": "quay.io/pterodactyl/core:java",
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

This endpoint retrieves information for the specified server using the external id.

### HTTP Request

`GET https://pterodactyl.app/api/application/servers/external/<external-id>` 






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
  	"external_id": "test_server",
  	"name": "Test",
  	"user": 1,
  	"description": "Test server",
  	"egg": 15,
  	"pack": 1,
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
    "allocation": {
      "default": 28,
      "additional": [
        3,
        19
      ],
    },
  	"deploy": {
  		"locations": [1],
  		"dedicated_ip": false,
  		"port_range": []
  	},
  	"start_on_completion": true,
  	"skip_scripts": false,
  	"oom_disabled": true
  }'
```
> The above command returns JSON structured like this:

```json
{
  "object": "server",
  "attributes": {
    "id": 53,
    "external_id": "test_server",
    "uuid": "d7bcc254-e218-4522-a7fe-9d2d562ad790",
    "identifier": "d7bcc254",
    "name": "Test",
    "description": "Test server",
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
    "pack": 1,
    "container": {
      "startup_command": "java -Xms128M -Xmx 1024M -jar server.jar",
      "image": "quay.io/pterodactyl/core:java-glibc",
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

Parameter | Information | Rules
- | - | -
external_id | The server's external id | <code>sometimes&#124;nullable&#124;string&#124;between:1,191&#124;unique:servers</code>
name | The server's name | <code>required&#124;string&#124;min:1&#124;max:255</code>
user | The user id of the server owner | <code>required&#124;integer&#124;exists:users,id</code>
description | The server's description | <code>sometimes&#124;string</code>
egg | The server's egg id | <code>required&#124;exists:eggs,id</code>
pack | The server's pack id | <code>sometimes&#124;nullable&#124;numeric&#124;min:0</code>
docker_image | The server's docker image | <code>sometimes&#124;string&#124;max:255</code>
startup | The server's startup command | <code>required&#124;string</code>
limits | The server's limits (array) | <code>required&#124;array</code>
limits.memory | The server's memory limit | <code>required&#124;numeric&#124;min:0</code>
limits.swap | The server's swap limit | <code>required&#124;numeric&#124;min:-1</code>
limits.disk | The server's disk limit | <code>required&#124;numeric&#124;min:0</code>
limits.io | The server's io limit | <code>required&#124;numeric&#124;between:10,1000</code>
limits.cpu | The server's cpu limit | <code>required&#124;numeric&#124;min:0</code>
feature_limits | The server's feature limits (array) | <code>required&#124;array</code>
feature_limits.databases | The server's database limit | <code>present&#124;nullable&#124;integer&#124;min:0</code>
feature_limits.allocations | The server's allocation limit | <code>present&#124;nullable&#124;integer&#124;min:0</code>
environment | The server's environment variables (related to the egg) | <code>present&#124;array</code>
allocation | The server's allocation ids (array) | <code>sometimes&#124;array</code>
allocation.default | The server's default allocation id | <code>sometimes&#124;bail&#124;unique:servers&#124;exists:allocations,id</code>
allocation.additional | The server's additional allocation ids (array) | <code>sometimes&#124;array</code>
allocation.additional.* | The server's additional allocation id | <code>exists:allocations,id</code>
deploy | The server's deploy information (array) | <code>sometimes&#124;required&#124;array</code>
deploy.locations | The server's deploy locations (array) | <code>array</code>
deploy.locations.* | The server's deploy location | <code>integer&#124;min:1</code>
deploy.dedicated_ip | The server's dedicated ip | <code>required_with:deploy,boolean</code>
deploy.port_range | The server's port ranges (array) | <code>array</code>
deploy.port_range.* | The server's port range | <code>string</code>
start_on_completion | Whether the server should start once created | <code>sometimes&#124;boolean</code>
skip_scripts | Whether the server should skip egg scripts | <code>sometimes&#124;boolean</code>
oom_disabled | Whether the server should have oom killer disabled | <code>sometimes&#124;boolean</code>






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
    "external_id": "cow_eater",
    "name": "Eat Cows",
    "user": "1",
    "description": "ok...."
  }'
```
> The above command returns JSON structured like this:

```json
{
  "object": "server",
  "attributes": {
    "id": 7,
    "external_id": "cow_eater",
    "uuid": "78165af0-4835-405f-b281-07e961bfd0ad",
    "identifier": "78165af0",
    "name": "Eat Cows",
    "description": "ok....",
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
      "image": "quay.io/pterodactyl/core:java",
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

This endpoint retrieves the details for the specified server.

### HTTP Request

`PATCH https://pterodactyl.app/api/application/servers/<internal-id>/details` 

Parameter | Information | Rules
- | - | -
external_id | The server's external id | <code>sometimes&#124;nullable&#124;string&#124;between:1,191&#124;unique:servers</code>
name | The server's name | <code>required&#124;string&#124;min:1&#124;max:255</code>
user | The user id of the server owner | <code>required&#124;integer&#124;exists:users,id</code>
description | The server's description | <code>sometimes&#124;nullable&#124;string</code>






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
    "allocation": 9,
    "oom_disabled": true,
    "limits": {
      "memory": 2048,
      "swap": -1,
      "disk": 10000,
      "io": 500,
      "cpu": 300
    },
    "add_allocations": [
      15
    ],
    "remove_allocations": [
      3
    ],
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
      "image": "quay.io/pterodactyl/core:java",
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

This endpoint retrieves the build information for the specified server.

### HTTP Request

`PATCH https://pterodactyl.app/api/application/servers/<internal-id>/build` 

Parameter | Information | Rules
- | - | -
allocation | The server's default allocation id | <code>required&#124;bail&#124;unique:servers&#124;exists:allocations,id</code>
oom_disabled | Whether the server should have oom killer disabled | <code>sometimes&#124;boolean</code>
limits | The server's limits (array) | <code>sometimes&#124;array</code>
limits.memory | The server's memory limit | <code>sometimes&#124;numeric&#124;min:0</code>
limits.swap | The server's swap limit | <code>sometimes&#124;numeric&#124;min:-1</code>
limits.disk | The server's disk limit | <code>sometimes&#124;numeric&#124;min:0</code>
limits.io | The server's io limit | <code>sometimes&#124;numeric&#124;between:10,1000</code>
limits.cpu | The server's cpu limit | <code>sometimes&#124;numeric&#124;min:0</code>
add_allocations | The allocation ids to be added to the server (array) | <code>sometimes&#124;bail&#124;array</code>
add_allocations.* | The allocation id to be added to the server | <code>integer</code>
remove_allocations | The allocation ids to be removed from the server (array) | <code>sometimes&#124;bail&#124;array</code>
remove_allocations.* | The allocation id to be removed from the server | <code>integer</code>
feature_limits | The server's feature limits (array) | <code>required&#124;array</code>
feature_limits.databases | The server's database limit | <code>present&#124;nullable&#124;integer&#124;min:0</code>
feature_limits.allocations | The server's allocation limit | <code>sometimes&#124;nullable&#124;integer&#124;min:0</code>

<aside class="warning">
The following parameters are deprecated, don't start using them and remove them if are.
</aside>

Parameter | Information | Rules
- | - | -
memory | The server's memory limit | <code>required_without:limits&#124;numeric&#124;min:0</code>
swap | The server's swap limit | <code>required_without:limits&#124;numeric&#124;min:-1</code>
disk | The server's disk limit | <code>required_without:limits&#124;numeric&#124;min:0</code>
io | The server's io limit | <code>required_without:limits&#124;numeric&#124;between:10,1000</code>
cpu | The server's cpu limit | <code>required_without:limits&#124;numeric&#124;min:0</code>





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
    "egg": 1,
    "pack": 4,
    "image": "quay.io/pterodactyl/core:java",
    "skip_scripts": false
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
      "image": "quay.io/pterodactyl/core:java",
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

This endpoint retrieves the startup information for the specified server.

### HTTP Request

`PATCH https://pterodactyl.app/api/application/servers/<internal-id>/startup` 

Parameter | Information | Rules
- | - | -
startup | The server's startup command | <code>required&#124;string</code>
environment | The server's environment variables (related to the egg) | <code>present&#124;array</code>
egg | The server's egg id | <code>required&#124;exists:eggs,id</code>
pack | The server's pack id | <code>sometimes&#124;nullable&#124;numeric&#124;min:0</code>
image | The server's docker image | <code>required&#124;string&#124;max:255</code>
skip_scripts | Whether the server should skip egg scripts | <code>present&#124;boolean</code>




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

This endpoint suspends the specified server.

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

This endpoint unsuspends the specified server.

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

This endpoint reinstalls the specified server.

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

This endpoint rebuilds the specified server.

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

This endpoint deletes the specified server.

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

This endpoint forcefully deletes the specified server.

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
{
  "object": "list",
  "data": [
    {
      "object": "server_database",
      "attributes": {
        "id": 6,
        "server": 1,
        "host": 2,
        "database": "s1_test",
        "username": "u1_iff9TGoHFt",
        "remote": "%",
        "created_at": "2019-10-06T15:16:26+02:00",
        "updated_at": "2019-10-06T15:28:26+02:00"
      }
    },
    {
      "object": "server_database",
      "attributes": {
        "id": 7,
        "server": 1,
        "host": 2,
        "database": "s1_db2",
        "username": "u1_tZ14uEvXan",
        "remote": "%",
        "created_at": "2019-10-06T15:28:57+02:00",
        "updated_at": "2019-10-06T15:28:57+02:00"
      }
    }
  ]
}
```

This endpoint retrieves all the databases for the specified server, along with information about them.

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
{
  "object": "server_database",
  "attributes": {
    "id": 6,
    "server": 1,
    "host": 2,
    "database": "s1_test",
    "username": "u1_iff9TGoHFt",
    "remote": "%",
    "created_at": "2019-10-06T15:16:26+02:00",
    "updated_at": "2019-10-06T15:28:26+02:00"
  }
}
```

This endpoint retrieves information about the specified database for the specified server.

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
  -X POST \
  -d '{
    "database": "mydb",
    "remote": "%",
    "host": 2
  }
```
> The above command returns JSON structured like this:

```json
{
  "object": "server_database",
  "attributes": {
    "id": 8,
    "server": 1,
    "host": 2,
    "database": "s1_mydb",
    "username": "u1_9qUoCWnpfS",
    "remote": "%",
    "created_at": "2019-10-06T15:53:31+02:00",
    "updated_at": "2019-10-06T15:53:31+02:00"
  },
  "meta": {
    "resource": "https://pterodactyl.app/api/application/servers/1/databases/8"
  }
}
```

This endpoint creates a new database on the specified server with the provided information.

### HTTP Request

`POST https://pterodactyl.app/api/application/servers/<internal-id>/databases` 

Parameter | Information | Rules
- | - | -
database | The database's name | <code>required&#124;string&#124;min:1&#124;max:24</code> + unique in `databases` where `database_host_id` = `host`
remote | The database's remote connection rule | <code>required&#124;string&#124;regex:/^[0-9%.]{1,15}$/</code>
host | The database's host server id | <code>required&#124;integer&#124;exists:database_hosts,id</code>






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

This endpoint edits the specified database on the specified server with the provided information.

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

This endpoint deletes the specified database on the specified server.

### HTTP Request

`DELETE https://pterodactyl.app/api/application/servers/<internal-id>/databases/<database-id>`