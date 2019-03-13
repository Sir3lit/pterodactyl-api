
# API - Application - Nodes

<!--
######################################
  ==> GET /api/application/nodes
######################################
-->
## List nodes


```shell
curl "https://pterodactyl.app/api/application/nodes" \
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
      "object": "node",
      "attributes": {
        "id": 2,
        "public": true,
        "name": "Test",
        "description": "Test",
        "location_id": 1,
        "fqdn": "fsn1.matthewp.io",
        "scheme": "https",
        "behind_proxy": false,
        "maintenance_mode": false,
        "memory": 4096,
        "memory_overallocate": 0,
        "disk": 10000,
        "disk_overallocate": 0,
        "upload_size": 100,
        "daemon_listen": 2096,
        "daemon_sftp": 2022,
        "daemon_base": "\/tmp\/daemon-data",
        "created_at": "2018-04-06T02:19:33+00:00",
        "updated_at": "2018-10-28T01:13:03+00:00"
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

`GET https://pterodactyl.app/api/application/nodes` 






<!--
######################################
  ==> GET /api/application/nodes/{node}
######################################
-->
## Get node information


```shell
curl "https://pterodactyl.app/api/application/nodes/<node-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```
> The above command returns JSON structured like this:

```json
{
  "object": "node",
  "attributes": {
    "id": 2,
    "public": true,
    "name": "Test",
    "description": "Test",
    "location_id": 1,
    "fqdn": "fsn1.matthewp.io",
    "scheme": "https",
    "behind_proxy": false,
    "maintenance_mode": false,
    "memory": 4096,
    "memory_overallocate": 0,
    "disk": 10000,
    "disk_overallocate": 0,
    "upload_size": 100,
    "daemon_listen": 2096,
    "daemon_sftp": 2022,
    "daemon_base": "\/tmp\/daemon-data",
    "created_at": "2018-04-06T02:19:33+00:00",
    "updated_at": "2018-10-28T01:13:03+00:00"
  }
}
```

This endpoint does this and that.

### HTTP Request

`GET https://pterodactyl.app/api/application/nodes/<node-id>` 






<!--
######################################
  ==> POST /api/application/nodes
######################################
-->
## Create node


```shell
curl "https://pterodactyl.app/api/application/nodes" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST \
  -d '
  {
    "name":"Test API Creation",
    "location_id":"1",
    "public":"1",
    "fqdn":"google.com",
    "scheme":"https",
    "behind_proxy":"0",
    "daemonBase":"/srv/daemon-data",
    "memory":1024,
    "memory_overallocate":0,
    "disk":1024,
    "disk_overallocate":0,
    "daemon_base":"/srv/daemon-data",
    "daemon_listen":"8080",
    "daemon_sftp":"2022",
    "throttle":{
      "enabled":false
    }
  }'
```
> The above command returns JSON structured like this:

```json
{
  "object": "node",
  "attributes": {
    "id": 4,
    "public": true,
    "name": "Test Node",
    "description": "",
    "location_id": 1,
    "fqdn": "node-01.pterodactyl.local",
    "scheme": "https",
    "behind_proxy": false,
    "maintenance_mode": false,
    "memory": 1024,
    "memory_overallocate": 0,
    "disk": 1024,
    "disk_overallocate": 0,
    "upload_size": 100,
    "daemon_listen": 8080,
    "daemon_sftp": 2022,
    "daemon_base": "\/srv\/daemon-data",
    "created_at": "2018-11-20T03:45:26+00:00",
    "updated_at": "2018-11-20T03:45:26+00:00"
  },
  "meta": {
    "resource": "https:\/\/pterodactyl.development.deluxenode.com\/api\/application\/nodes\/4"
  }
}
```

This endpoint does this and that.

### HTTP Request

`POST https://pterodactyl.app/api/application/nodes` 






<!--
######################################
  ==> PATCH /api/application/nodes/{node}
######################################
-->
## Edit node


```shell
curl "https://pterodactyl.app/api/application/nodes/<node-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X PATCH \
  -d '
  {
    "name": "Test Node 2",
    "location_id": "1",
    "public": "1",
    "fqdn": "pdev1.pterodactyl.development.deluxenode.com",
    "scheme": "https",
    "behind_proxy": "0",
    "daemonBase": "/srv/daemon-data",
    "memory": 1024,
    "memory_overallocate": 0,
    "disk": 1024,
    "disk_overallocate": 0,
    "daemon_base": "/srv/daemon-data",
    "daemon_listen": "8080",
    "daemon_sftp": "2022",
    "throttle": {
      "enabled": false
    }
  }'
```
> The above command returns JSON structured like this:

```json
{
  "object": "node",
  "attributes": {
    "id": 2,
    "public": true,
    "name": "Test Node 2",
    "description": "Test",
    "location_id": 1,
    "fqdn": "pdev1.pterodactyl.development.deluxenode.com",
    "scheme": "https",
    "behind_proxy": false,
    "maintenance_mode": false,
    "memory": 1024,
    "memory_overallocate": 0,
    "disk": 1024,
    "disk_overallocate": 0,
    "upload_size": 100,
    "daemon_listen": 8080,
    "daemon_sftp": 2022,
    "daemon_base": "\/srv\/daemon-data",
    "created_at": "2018-04-06T02:19:33+00:00",
    "updated_at": "2018-12-17T19:37:26+00:00"
  }
}
```

This endpoint does this and that.

### HTTP Request

`PATCH https://pterodactyl.app/api/application/nodes/<node-id>` 






<!--
######################################
  ==> DELETE /api/application/nodes/{node}
######################################
-->
## Delete node


```shell
curl "https://pterodactyl.app/api/application/nodes/<node-id>" \
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

`DELETE https://pterodactyl.app/api/application/nodes/<node-id>` 






<!--
######################################
  ==> GET /api/application/nodes/{node}/allocations
######################################
-->
## List specific node allocations


```shell
curl "https://pterodactyl.app/api/application/nodes/<node-id>/allocations" \
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
      "object": "allocation",
      "attributes": {
        "id": 3,
        "ip": "195.201.194.74",
        "alias": null,
        "port": 25499,
        "assigned": true
      }
    },
    {
      "object": "allocation",
      "attributes": {
        "id": 4,
        "ip": "195.201.194.74",
        "alias": null,
        "port": 25566,
        "assigned": true
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

`GET https://pterodactyl.app/api/application/nodes/<node-id>/allocations` 






<!--
######################################
  ==> POST /api/application/nodes/{node}/allocations
######################################
-->
## Create allocation


```shell
curl "https://pterodactyl.app/api/application/nodes/<node-id>/allocations" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST \
  -d '
  {
    "ip": "1.1.1.1",
    "alias": "one.one.one.one",
    "ports": [
      "4000"
    ]
  }'
```
> The above command returns JSON structured like this:

```json
{
  "errors": [
    {
      "code": "FatalThrowableError",
      "status": "500",
      "detail": "Return value of Pterodactyl\\Http\\Controllers\\Api\\Application\\Nodes\\AllocationController::store() must be of the type array, object returned",
      "source": {
        "line": 85,
        "file": "/app/Http/Controllers/Api/Application/Nodes/AllocationController.php"
      } 
    }
  ]
}
```

This endpoint does this and that.

### HTTP Request

`POST https://pterodactyl.app/api/application/nodes/<node-id>/allocations` 






<!--
######################################
  ==> POST /api/application/nodes/{node}/allocations/{allocation}
######################################
-->
## Delete allocation


```shell
curl "https://pterodactyl.app/api/application/nodes/<node-id>/allocations/<allocation-id>" \
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

`DELETE https://pterodactyl.app/api/application/nodes/<node-id>/allocations/<allocation-id>`