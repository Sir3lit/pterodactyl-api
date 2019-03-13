
# API - Client 

<!--########################################## -->
<!--   ==> List all servers                    -->
<!--########################################## -->
## List all servers
```shell
curl "https://pterodactyl.app/api/client" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```
> The above command returns JSON structured like this:

```json
{
   "object":"list",
   "data":[
      {
         "object":"server",
         "attributes":{
            "server_owner":true,
            "identifier":"d3aac109",
            "uuid":"d3aac109-e5a0-4331-b03e-3454f7e136dc",
            "name":"Survival",
            "description":"",
            "limits":{
               "memory":1024,
               "swap":0,
               "disk":5000,
               "io":500,
               "cpu":200
            },
            "feature_limits":{
               "databases":5,
               "allocations":5
            }
         }
      }
   ],
   "meta":{
      "pagination":{
         "total":1,
         "count":1,
         "per_page":25,
         "current_page":1,
         "total_pages":1,
         "links":[

         ]
      }
   }
}
```

This endpoint retrieves all servers that the user has access to, along with information about them.

### HTTP Request

`GET https://pterodactyl.app/api/client` 






<!--########################################## -->
<!--   ==> Get server specific information     -->
<!--########################################## -->
## Get server specific information

```shell
curl "https://pterodactyl.app/api/client/servers/<id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```

> The above command returns JSON structured like this:

```json
{
   "object":"server",
   "attributes":{
      "server_owner":true,
      "identifier":"d3aac109",
      "uuid":"d3aac109-e5a0-4331-b03e-3454f7e136dc",
      "name":"Survival",
      "description":"",
      "limits":{
         "memory":1024,
         "swap":0,
         "disk":5000,
         "io":500,
         "cpu":200
      },
      "feature_limits":{
         "databases":5,
         "allocations":5
      }
   }
}
```

This endpoint retrieves information for the specified server.

### HTTP Request

`GET https://pterodactyl.app/api/client/servers/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the server that you are requesting. 






<!--########################################## -->
<!--   ==> Get server resource utilization     -->
<!--########################################## -->
## Get server resource utilization

```shell
curl "https://pterodactyl.app/api/client/servers/<id>/utilization" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET
```

> The above command returns JSON structured like this:

```json
{
   "object":"stats",
   "attributes":{
      "state":"on",
      "memory":{
         "current":375,
         "limit":1024
      },
      "cpu":{
         "current":1.522,
         "cores":[
            0.033,
            0.048,
            0.04,
            0,
            0.031,
            0,
            0.021,
            0.024,
            0.249,
            0.042,
            0.007,
            0,
            0.293,
            0.003,
            0.6,
            0.131
         ],
         "limit":200
      },
      "disk":{
         "current":119,
         "limit":5000
      }
   }
}
``` 

This endpoint displays resource utilization of the specified server.

<aside class="notice">
If the server is offline, current data is displayed as <code>0</code> and the state is displayed as <code>off</code>.
</aside>

### HTTP Request

`GET https://pterodactyl.app/api/client/servers/<ID>/utilization`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the server that you are requesting. 






<!--########################################## -->
<!--   ==> Send console command                -->
<!--########################################## -->
## Send console command

```shell
curl "https://pterodactyl.app/api/client/servers/<id>/command" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST \
  -d '{ "command": "say CodeCo says Hi!" }'
```

This endpoint sends a command to the server.

You are required to add the `Accept: Application/vnd.pterodactyl.v1+json` and `Content-Type: application/json` headers for this endpoint.

If successful, there will be an empty response body.

<aside class="warning">
The server must be online already, otherwise you will receive a <code>HTTP 412</code>error.
</aside>

### HTTP Request

`POST https://pterodactyl.app/api/client/servers/<ID>/command`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the server that you are requesting.
command | The command that you would like sent to the server. 






<!--########################################## -->
<!--   ==> Send power action                   -->
<!--########################################## -->
## Send power action

```shell
curl "https://pterodactyl.app/api/client/servers/<id>/power" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X POST \
  -d '{ "signal": "start" }'
```

This endpoint sends a power signal to the server.

You are required to add the `Accept: Application/vnd.pterodactyl.v1+json` and `Content-Type: application/json` headers for this endpoint.

If successful, there will be an empty response body.

### HTTP Request

`POST https://pterodactyl.app/api/client/servers/<ID>/power`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the server that you are requesting.
signal | The power signal you want to send to the server.

### Power Signals

Signal | Description
--------- | -----------
start | Sends the startup command to the server.
stop | Sends the stop command to the server.
restart | Stops the server then immediately starts it straight after.
kill | Instantly ends all processes and marks the server as stopped.

<aside class="warning">
Sending the <code>kill</code> power signal will forcefully kill the server process and can cause corruption in files, only use it as a last resort.
</aside>