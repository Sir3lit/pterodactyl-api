
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
        "daemon_base": "/tmp/daemon-data",
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

This endpoint retrieves all nodes on the panel along with information about them.

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
    "daemon_base": "/tmp/daemon-data",
    "created_at": "2018-04-06T02:19:33+00:00",
    "updated_at": "2018-10-28T01:13:03+00:00"
  }
}
```

This endpoint retrieves information for the specified node.

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
    "name": "Test Node",
    "description": "",
    "location_id": 1,
    "public": true,
    "fqdn": "node-01.pterodactyl.app",
    "scheme": "https",
    "behind_proxy": false,
    "memory": 1024,
    "memory_overallocate": 0,
    "disk": 1024,
    "disk_overallocate": 0,
    "daemon_base": "/srv/daemon-data",
    "daemon_listen": "8080",
    "daemon_sftp": "2022",
    "maintenance_mode": false,
    "upload_size": 100,
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
    "fqdn": "node-01.pterodactyl.app",
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
    "daemon_base": "/srv/daemon-data",
    "created_at": "2018-11-20T03:45:26+00:00",
    "updated_at": "2018-11-20T03:45:26+00:00"
  },
  "meta": {
    "resource": "https://pterodactyl.app/api/application/nodes/4"
  }
}
```

This endpoint creates a new node with the provided information.

### HTTP Request

`POST https://pterodactyl.app/api/application/nodes` 

Parameter | Information | Rules
- | - | -
name | The node's name | <code>required&#124;regex:/^([\w .-]{1,100})$/</code>
description | The node's description | <code>sometimes&#124;string</code>
location_id | The node's location id | <code>required&#124;exists:locations,id</code>
public | Whether auto-deployment is enabled for this node | <code>sometimes&#124;boolean</code>
fqdn | The node's fully qualified domain name| <code>required&#124;string</code>
scheme | The node's connection scheme | <code>required&#124;in:http,https</code>
behind_proxy | Whether the node is behind a proxy| <code>sometimes&#124;boolean</code>
memory | The node's memory *in mb* | <code>required&#124;numeric&#124;min:1</code>
memory_overallocate | The node's memory over-allocation *in %* | <code>required&#124;numeric&#124;min:-1</code>
disk | The node's disk space *in mb* | <code>required&#124;numeric&#124;min:1</code>
disk_overallocate | The node's disk space over-allocation *in %* | <code>required&#124;numeric&#124;min:-1</code>
daemon_base | The node's base daemon path | <code>sometimes&#124;regex:/^([\/][\d\w.\-\/]+)$/</code>
daemon_sftp | The node's daemon sftp port | <code>required&#124;numeric&#124;between:1,65535</code>
daemon_listen | The node's daemon port | <code>required&#124;numeric&#124;between:1,65535</code>
maintenance_mode | Whether the node is in maintenance mode | <code>sometimes&#124;boolean</code>
upload_size | The node's upload size limit | <code>sometimes&#124;int&#124;between:1,1024</code>





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
    "name": "Test Node",
    "description": "Test",
    "location_id": 5,
    "public": true,
    "fqdn": "pdev1.pterodactyl.app",
    "scheme": "https",
    "behind_proxy": false,
    "memory": 2048,
    "memory_overallocate": 0,
    "disk": 1024,
    "disk_overallocate": -1,
    "daemon_base": "/srv/daemon-data",
    "daemon_listen": "8080",
    "daemon_sftp": "2022",
    "maintenance_mode": false,
    "upload_size": 100,
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
    "location_id": 5,
    "fqdn": "pdev1.pterodactyl.app",
    "scheme": "https",
    "behind_proxy": false,
    "maintenance_mode": false,
    "memory": 2048,
    "memory_overallocate": 0,
    "disk": 1024,
    "disk_overallocate": -1,
    "upload_size": 100,
    "daemon_listen": 8080,
    "daemon_sftp": 2022,
    "daemon_base": "/srv/daemon-data",
    "created_at": "2018-04-06T02:19:33+00:00",
    "updated_at": "2018-12-17T19:37:26+00:00"
  }
}
```

This endpoint edits the specified node with the provided information.

### HTTP Request

`PATCH https://pterodactyl.app/api/application/nodes/<node-id>` 

Parameter | Information | Rules
- | - | -
name | The node's name | <code>required&#124;regex:/^([\w .-]{1,100})$/</code>
description | The node's description | <code>sometimes&#124;string</code>
location_id | The node's location id | <code>required&#124;exists:locations,id</code>
public | Whether auto-deployment is enabled for this node | <code>sometimes&#124;boolean</code>
fqdn | The node's fully qualified domain name| <code>required&#124;string</code>
scheme | The node's connection scheme | <code>required&#124;in:http,https</code>
behind_proxy | Whether the node is behind a proxy| <code>sometimes&#124;boolean</code>
memory | The node's memory *in mb* | <code>required&#124;numeric&#124;min:1</code>
memory_overallocate | The node's memory over-allocation *in %* | <code>required&#124;numeric&#124;min:-1</code>
disk | The node's disk space *in mb* | <code>required&#124;numeric&#124;min:1</code>
disk_overallocate | The node's disk space over-allocation *in %* | <code>required&#124;numeric&#124;min:-1</code>
daemon_base | The node's base daemon path | <code>sometimes&#124;regex:/^([\/][\d\w.\-\/]+)$/</code>
daemon_sftp | The node's daemon sftp port | <code>required&#124;numeric&#124;between:1,65535</code>
daemon_listen | The node's daemon port | <code>required&#124;numeric&#124;between:1,65535</code>
maintenance_mode | Whether the node is in maintenance mode | <code>sometimes&#124;boolean</code>
upload_size | The node's upload size limit | <code>sometimes&#124;int&#124;between:1,1024</code>






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

This endpoint deletes the specified node.

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

This endpoint retrieves all allocations for the specified node, along with information about them.

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

This endpoint creates a new allocation using the provided  information.

### HTTP Request

`POST https://pterodactyl.app/api/application/nodes/<node-id>/allocations` 

Parameter | Information | Rules
- | - | -
ip | The allocation's ip | <code>required&#124;string</code>
alias | The allocation's alias name | <code>sometimes&#124;nullable&#124;string&#124;max:255</code>
ports | The allocation ports (array) | <code>required&#124;array</code>
ports.* | The allocation port | <code>string</code>





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

This endpoint deletes the specified allocation for the specified node.

### HTTP Request

`DELETE https://pterodactyl.app/api/application/nodes/<node-id>/allocations/<allocation-id>`