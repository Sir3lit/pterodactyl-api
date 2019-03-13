
# API - Application - Nests

<!--
######################################
  ==> GET /api/application/nests
######################################
-->
## List nests


```shell
curl "https://pterodactyl.app/api/application/nests" \
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
      "object": "nest",
      "attributes": {
        "id": 1,
        "uuid": "179a06c9-b5bf-4798-8c0e-9f78e8f1f67f",
        "author": "support@pterodactyl.io",
        "name": "Minecraft",
        "description": "Minecraft - the classic game from Mojang. With support for Vanilla MC, Spigot, and many others!",
        "created_at": "2018-03-18T15:14:37+00:00",
        "updated_at": "2018-03-18T15:14:37+00:00"
      }
    },
    {
      "object": "nest",
      "attributes": {
        "id": 2,
        "uuid": "c389ab01-8b30-4c0f-b2a2-01e79b3611d2",
        "author": "support@pterodactyl.io",
        "name": "Source Engine",
        "description": "Includes support for most Source Dedicated Server games.",
        "created_at": "2018-03-18T15:14:37+00:00",
        "updated_at": "2018-03-18T15:14:37+00:00"
      }
    },
    {
      "object": "nest",
      "attributes": {
        "id": 3,
        "uuid": "8b47c310-ff04-4c10-84c8-133e63f1bf61",
        "author": "support@pterodactyl.io",
        "name": "Voice Servers",
        "description": "Voice servers such as Mumble and Teamspeak 3.",
        "created_at": "2018-03-18T15:14:37+00:00",
        "updated_at": "2018-03-18T15:14:37+00:00"
      }
    },
    {
      "object": "nest",
      "attributes": {
        "id": 4,
        "uuid": "f92cd279-a916-4ede-84ee-900f51048e31",
        "author": "support@pterodactyl.io",
        "name": "Rust",
        "description": "Rust - A game where you must fight to survive.",
        "created_at": "2018-03-18T15:14:37+00:00",
        "updated_at": "2018-03-18T15:14:37+00:00"
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

`GET https://pterodactyl.app/api/application/nodes` 






<!--
######################################
  ==> GET /api/application/nests/{nest}
######################################
-->
## Get nest information


```shell
curl "https://pterodactyl.app/api/application/nests/<nest-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```
> The above command returns JSON structured like this:

```json
{
  "object": "nest",
  "attributes": {
    "id": 1,
    "uuid": "179a06c9-b5bf-4798-8c0e-9f78e8f1f67f",
    "author": "support@pterodactyl.io",
    "name": "Minecraft",
    "description": "Minecraft - the classic game from Mojang. With support for Vanilla MC, Spigot, and many others!",
    "created_at": "2018-03-18T15:14:37+00:00",
    "updated_at": "2018-03-18T15:14:37+00:00"
  }
}
```

This endpoint does this and that.

### HTTP Request

`GET https://pterodactyl.app/api/application/nodes/<node-id>` 






<!--
######################################
  ==> GET /api/application/nests/{nest}/eggs
######################################
-->
## Get eggs in nest


```shell
curl "https://pterodactyl.app/api/application/nests/<nest-id>/eggs" \
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
      "object": "egg",
      "attributes": {
        "id": 1,
        "uuid": "db6323d7-d62f-4278-bb66-db06484b1089",
        "nest": 1,
        "author": "support@pterodactyl.io",
        "description": "Spigot is the most widely-used modded Minecraft server software in the world. It powers many of the top Minecraft server networks around to ensure they can cope with their huge player base and ensure the satisfaction of their players. Spigot works by reducing and eliminating many causes of lag, as well as adding in handy features and settings that help make your job of server administration easier.",
        "docker_image": "quay.io\/pterodactyl\/core:java-glibc",
        "config": {
          "files": {
            "server.properties": {
              "parser": "properties",
              "find": {
                "server-ip": "0.0.0.0",
                "enable-query": "true",
                "server-port": "{{server.build.default.port}}",
                "query.port": "{{server.build.default.port}}"
              }
            }
          },
          "startup": {
            "done": ")! For help, type ",
            "userInteraction": [
              "Go to eula.txt for more info."
            ]
          },
          "stop": "stop",
          "logs": {
            "custom": false,
            "location": "logs\/latest.log"
          },
          "extends": null
        },
        "startup": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
        "script": {
          "privileged": true,
          "install": "#!\/bin\/ash\r\n# Spigot Installation Script\r\n#\r\n# Server Files: \/mnt\/server\r\n\r\n## Only download if a path is provided, otherwise continue.\r\nif [ ! -z \"${DL_PATH}\" ]; then\r\n    apk update\r\n    apk add curl\r\n\r\n    cd \/mnt\/server\r\n\r\n    MODIFIED_DOWNLOAD=`eval echo $(echo ${DL_PATH} | sed -e 's\/{{\/${\/g' -e 's\/}}\/}\/g')`\r\n    curl -sSL -o ${SERVER_JARFILE} ${MODIFIED_DOWNLOAD}\r\nelse\r\n    apk add --no-cache curl git openjdk8 openssl\r\n    \r\n    cd \/srv\/\r\n    \r\n    wget https:\/\/hub.spigotmc.org\/jenkins\/job\/BuildTools\/lastSuccessfulBuild\/artifact\/target\/BuildTools.jar\r\n    \r\n    mv BuildTools.jar \/srv\/\r\n\r\n    java -jar BuildTools.jar --rev ${DL_VERSION}\r\n\r\n    mv spigot-*.jar \/mnt\/server\/${SERVER_JARFILE}\r\nfi",
          "entry": "ash",
          "container": "alpine:3.7",
          "extends": null
        },
        "created_at": "2018-03-18T15:14:37+00:00",
        "updated_at": "2018-07-08T00:56:48+00:00"
      }
    },
    {
      "object": "egg",
      "attributes": {
        "id": 2,
        "uuid": "2f9bfca1-4a41-4302-83e9-0aa868719eb6",
        "nest": 1,
        "author": "support@pterodactyl.io",
        "description": "Minecraft Forge Server. Minecraft Forge is a modding API (Application Programming Interface), which makes it easier to create mods, and also make sure mods are compatible with each other.",
        "docker_image": "quay.io\/pterodactyl\/core:java",
        "config": {
          "files": {
            "server.properties": {
              "parser": "properties",
              "find": {
                "server-ip": "0.0.0.0",
                "enable-query": "true",
                "server-port": "{{server.build.default.port}}",
                "query.port": "{{server.build.default.port}}"
              }
            }
          },
          "startup": {
            "done": ")! For help, type ",
            "userInteraction": [
              "Go to eula.txt for more info."
            ]
          },
          "stop": "stop",
          "logs": {
            "custom": false,
            "location": "logs\/latest.log"
          },
          "extends": null
        },
        "startup": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
        "script": {
          "privileged": true,
          "install": "#!\/bin\/ash\r\n# Forge Installation Script\r\n#\r\n# Server Files: \/mnt\/server\r\napk update\r\napk add curl\r\n\r\nif [ -z \"$MC_VERSION\" ] || [ \"$MC_VERSION\" == \"latest\" ]; then\r\n  FORGE_VERSION=$(curl -sl http:\/\/files.minecraftforge.net\/maven\/net\/minecraftforge\/forge\/ | grep -A1 Latest | grep  -o -e '[1]\\.[0-9][0-9]]\\?\\.\\?[0-9]\\?[0-9] - [0-9][0-9]\\.[0-9][0-9]\\.[0-9]\\?[0-9]\\.[0-9][0-9][0-9][0-9]' | sed 's\/ \/\/g')\r\nelse\r\n  FORGE_VERSION=$(curl -sl http:\/\/files.minecraftforge.net\/maven\/net\/minecraftforge\/forge\/index_$MC_VERSION.html | grep -A1 Latest | grep  -o -e '[1]\\.[0-9][0-9]]\\?\\.\\?[0-9]\\?[0-9] - [0-9][0-9]\\.[0-9][0-9]\\.[0-9]\\?[0-9]\\.[0-9][0-9][0-9][0-9]' | sed 's\/ \/\/g')\r\nfi\r\n\r\ncd \/mnt\/server\r\n\r\necho -e \"\\nDownloading Forge Version $FORGE_VERSION\\n\"\r\ncurl -sS http:\/\/files.minecraftforge.net\/maven\/net\/minecraftforge\/forge\/$FORGE_VERSION\/forge-$FORGE_VERSION-installer.jar -o installer.jar\r\ncurl -sS http:\/\/files.minecraftforge.net\/maven\/net\/minecraftforge\/forge\/$FORGE_VERSION\/forge-$FORGE_VERSION-universal.jar -o $SERVER_JARFILE\r\n\r\necho -e \"\\nInstalling forge server usint the installer jar file.\\n\"\r\njava -jar installer.jar --installServer\r\n\r\necho -e \"\\nDeleting installer jar file and cleaning up.\\n\"\r\nrm -rf installer.jar",
          "entry": "ash",
          "container": "frolvlad\/alpine-oraclejdk8:cleaned",
          "extends": null
        },
        "created_at": "2018-03-18T15:14:37+00:00",
        "updated_at": "2018-07-08T00:56:48+00:00"
      }
    },
    {
      "object": "egg",
      "attributes": {
        "id": 3,
        "uuid": "dd105df0-124e-4c1a-8738-caa9e457569f",
        "nest": 1,
        "author": "support@pterodactyl.io",
        "description": "For a long time, Minecraft server owners have had a dream that encompasses a free, easy, and reliable way to connect multiple Minecraft servers together. BungeeCord is the answer to said dream. Whether you are a small server wishing to string multiple game-modes together, or the owner of the ShotBow Network, BungeeCord is the ideal solution for you. With the help of BungeeCord, you will be able to unlock your community's full potential.",
        "docker_image": "quay.io\/pterodactyl\/core:java",
        "config": {
          "files": {
            "config.yml": {
              "parser": "yaml",
              "find": {
                "listeners[0].query_enabled": true,
                "listeners[0].query_port": "{{server.build.default.port}}",
                "listeners[0].host": "0.0.0.0:{{server.build.default.port}}",
                "servers.*.address": {
                  "127.0.0.1": "{{config.docker.interface}}",
                  "localhost": "{{config.docker.interface}}"
                }
              }
            }
          },
          "startup": {
            "done": "Listening on ",
            "userInteraction": [
              "Listening on \/0.0.0.0:25577"
            ]
          },
          "stop": "end",
          "logs": {
            "custom": false,
            "location": "proxy.log.0"
          },
          "extends": null
        },
        "startup": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
        "script": {
          "privileged": true,
          "install": "#!\/bin\/ash\n# Bungeecord Installation Script\n#\n# Server Files: \/mnt\/server\napk update\napk add curl\n\ncd \/mnt\/server\n\nif [ -z \"${BUNGEE_VERSION}\" ] || [ \"${BUNGEE_VERSION}\" == \"latest\" ]; then\n    BUNGEE_VERSION=\"lastStableBuild\"\nfi\n\ncurl -o ${SERVER_JARFILE} https:\/\/ci.md-5.net\/job\/BungeeCord\/${BUNGEE_VERSION}\/artifact\/bootstrap\/target\/BungeeCord.jar",
          "entry": "ash",
          "container": "alpine:3.4",
          "extends": null
        },
        "created_at": "2018-03-18T15:14:37+00:00",
        "updated_at": "2018-03-18T15:14:37+00:00"
      }
    },
    {
      "object": "egg",
      "attributes": {
        "id": 4,
        "uuid": "56af5379-7255-46af-b693-eb71b1ba4e90",
        "nest": 1,
        "author": "support@pterodactyl.io",
        "description": "Minecraft is a game about placing blocks and going on adventures. Explore randomly generated worlds and build amazing things from the simplest of homes to the grandest of castles. Play in Creative Mode with unlimited resources or mine deep in Survival Mode, crafting weapons and armor to fend off dangerous mobs. Do all this alone or with friends.",
        "docker_image": "quay.io\/pterodactyl\/core:java",
        "config": {
          "files": {
            "server.properties": {
              "parser": "properties",
              "find": {
                "server-ip": "0.0.0.0",
                "enable-query": "true",
                "server-port": "{{server.build.default.port}}",
                "query.port": "{{server.build.default.port}}"
              }
            }
          },
          "startup": {
            "done": ")! For help, type ",
            "userInteraction": [
              "Go to eula.txt for more info."
            ]
          },
          "stop": "stop",
          "logs": {
            "custom": false,
            "location": "logs\/latest.log"
          },
          "extends": null
        },
        "startup": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
        "script": {
          "privileged": true,
          "install": "#!\/bin\/ash\r\n# Vanilla MC Installation Script\r\n#\r\n# Server Files: \/mnt\/server\r\napk update\r\napk add curl jq\r\n\r\ncd \/mnt\/server\r\n\r\nLATEST_VERSION=`curl https:\/\/launchermeta.mojang.com\/mc\/game\/version_manifest.json | jq -r '.latest.release'`\r\n\r\nif [ -z \"$VANILLA_VERSION\" ] || [ \"$VANILLA_VERSION\" == \"latest\" ]; then\r\n  MANIFEST_URL=$(curl https:\/\/launchermeta.mojang.com\/mc\/game\/version_manifest.json | jq .versions | jq -r '.[] | select(.id == \"'$LATEST_VERSION'\") | .url')\r\nelse\r\n  MANIFEST_URL=$(curl https:\/\/launchermeta.mojang.com\/mc\/game\/version_manifest.json | jq .versions | jq -r '.[] | select(.id == \"'$VANILLA_VERSION'\") | .url')\r\nfi\r\n\r\nDOWNLOAD_URL=`curl $MANIFEST_URL | jq .downloads.server | jq -r '. | .url'`\r\n\r\ncurl -o ${SERVER_JARFILE} $DOWNLOAD_URL",
          "entry": "ash",
          "container": "alpine:3.7",
          "extends": null
        },
        "created_at": "2018-03-18T15:14:37+00:00",
        "updated_at": "2018-07-08T00:56:48+00:00"
      }
    },
    {
      "object": "egg",
      "attributes": {
        "id": 5,
        "uuid": "30bf5d10-9f37-4b58-9674-78b73a482e2a",
        "nest": 1,
        "author": "support@pterodactyl.io",
        "description": "SpongeVanilla is the SpongeAPI implementation for Vanilla Minecraft.",
        "docker_image": "quay.io\/pterodactyl\/core:java-glibc",
        "config": {
          "files": {
            "server.properties": {
              "parser": "properties",
              "find": {
                "server-ip": "0.0.0.0",
                "enable-query": "true",
                "server-port": "{{server.build.default.port}}",
                "query.port": "{{server.build.default.port}}"
              }
            }
          },
          "startup": {
            "done": ")! For help, type ",
            "userInteraction": [
              "Go to eula.txt for more info."
            ]
          },
          "stop": "stop",
          "logs": {
            "custom": false,
            "location": "logs\/latest.log"
          },
          "extends": null
        },
        "startup": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
        "script": {
          "privileged": true,
          "install": "#!\/bin\/ash\n# Sponge Installation Script\n#\n# Server Files: \/mnt\/server\n\napk update\napk add curl\n\ncd \/mnt\/server\n\ncurl -sSL \"https:\/\/repo.spongepowered.org\/maven\/org\/spongepowered\/spongevanilla\/${SPONGE_VERSION}\/spongevanilla-${SPONGE_VERSION}.jar\" -o ${SERVER_JARFILE}",
          "entry": "ash",
          "container": "alpine:3.4",
          "extends": null
        },
        "created_at": "2018-03-18T15:14:37+00:00",
        "updated_at": "2018-03-18T15:14:37+00:00"
      }
    },
    {
      "object": "egg",
      "attributes": {
        "id": 15,
        "uuid": "21a8b345-0d42-4c26-adc2-b2584a3bac83",
        "nest": 1,
        "author": "parker@parkervcp.com",
        "description": "The stupid chatbot parkertron by Parkervcp.\r\n\r\nhttps:\/\/github.com\/parkervcp\/parkertron",
        "docker_image": "quay.io\/parkervcp\/pterodactyl-images:parkertron",
        "config": {
          "files": [],
          "startup": {
            "done": "Bot is now running"
          },
          "stop": "^C",
          "logs": {
            "custom": false,
            "location": "logs\/latest.log"
          },
          "extends": null
        },
        "startup": ".\/parkertron",
        "script": {
          "privileged": true,
          "install": "#!\/bin\/ash\r\n# parkertron Installation Script\r\n#\r\n# Server Files: \/mnt\/server\r\nexport GOPATH=$HOME\/go\r\nexport PATH=$GOROOT\/bin:$GOPATH\/bin:$PATH\r\n\r\ncd\r\n\r\nmkdir -p go\/bin go\/src\r\n\r\napk add --no-cache --update go git curl lua-stdlib lua musl-dev g++ libc-dev tesseract-ocr tesseract-ocr-dev\r\n\r\necho \"installing dep for golang dependancies\"\r\n\r\ncurl https:\/\/raw.githubusercontent.com\/golang\/dep\/master\/install.sh | sh\r\n\r\ncd go\/src\/\r\n\r\necho \"pulling the parkertron pterodactyl branch\"\r\n\r\ngit clone https:\/\/github.com\/parkervcp\/parkertron.git\r\n\r\ncd parkertron\/\r\n\r\ndep ensure\r\n\r\necho \"building parkertron\"\r\n\r\ngo build \r\n\r\necho \"build complete copying parkertron and example configs over\"\r\n\r\ncp parkertron \/mnt\/server\/\r\n\r\nif [ -d \"$DIRECTORY\" ]; then\r\n    echo \"Files exist already\"\r\nelse\r\n    cp -r configs\/ \/mnt\/server\/\r\nfi\r\n\r\necho \"Install complete. If you watched this. Congrats.\"",
          "entry": "ash",
          "container": "alpine:3.7",
          "extends": null
        },
        "created_at": "2018-11-10T19:49:41+00:00",
        "updated_at": "2018-11-10T19:49:41+00:00"
      }
    }
  ]
}
```

This endpoint does this and that.

### HTTP Request

`GET https://pterodactyl.app/api/application/nodes` 






<!--
######################################
  ==> GET /api/application/nests/{nest}/eggs/{egg}
######################################
-->
## Get specific egg


```shell
curl "https://pterodactyl.app/api/application/nests/<nest-id>/eggs/<egg-id>" \
  -H "Authorization: Bearer meowmeowmeow" \
  -H "Content-Type: application/json" \
  -H "Accept: Application/vnd.pterodactyl.v1+json" \
  -X GET 
```
> The above command returns JSON structured like this:

```json
{
  "object": "egg",
  "attributes": {
    "id": 1,
    "uuid": "db6323d7-d62f-4278-bb66-db06484b1089",
    "nest": 1,
    "author": "support@pterodactyl.io",
    "description": "Spigot is the most widely-used modded Minecraft server software in the world. It powers many of the top Minecraft server networks around to ensure they can cope with their huge player base and ensure the satisfaction of their players. Spigot works by reducing and eliminating many causes of lag, as well as adding in handy features and settings that help make your job of server administration easier.",
    "docker_image": "quay.io\/pterodactyl\/core:java-glibc",
    "config": {
      "files": {
        "server.properties": {
          "parser": "properties",
          "find": {
            "server-ip": "0.0.0.0",
            "enable-query": "true",
            "server-port": "{{server.build.default.port}}",
            "query.port": "{{server.build.default.port}}"
          }
        }
      },
      "startup": {
        "done": ")! For help, type ",
        "userInteraction": [
          "Go to eula.txt for more info."
        ]
      },
      "stop": "stop",
      "logs": {
        "custom": false,
        "location": "logs\/latest.log"
      },
      "extends": null
    },
    "startup": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
    "script": {
      "privileged": true,
      "install": "#!\/bin\/ash\r\n# Spigot Installation Script\r\n#\r\n# Server Files: \/mnt\/server\r\n\r\n## Only download if a path is provided, otherwise continue.\r\nif [ ! -z \"${DL_PATH}\" ]; then\r\n    apk update\r\n    apk add curl\r\n\r\n    cd \/mnt\/server\r\n\r\n    MODIFIED_DOWNLOAD=`eval echo $(echo ${DL_PATH} | sed -e 's\/{{\/${\/g' -e 's\/}}\/}\/g')`\r\n    curl -sSL -o ${SERVER_JARFILE} ${MODIFIED_DOWNLOAD}\r\nelse\r\n    apk add --no-cache curl git openjdk8 openssl\r\n    \r\n    cd \/srv\/\r\n    \r\n    wget https:\/\/hub.spigotmc.org\/jenkins\/job\/BuildTools\/lastSuccessfulBuild\/artifact\/target\/BuildTools.jar\r\n    \r\n    mv BuildTools.jar \/srv\/\r\n\r\n    java -jar BuildTools.jar --rev ${DL_VERSION}\r\n\r\n    mv spigot-*.jar \/mnt\/server\/${SERVER_JARFILE}\r\nfi",
      "entry": "ash",
      "container": "alpine:3.7",
      "extends": null
    },
    "created_at": "2018-03-18T15:14:37+00:00",
    "updated_at": "2018-07-08T00:56:48+00:00"
  }
}
```

This endpoint does this and that.

### HTTP Request

`GET https://pterodactyl.app/api/application/nodes/<node-id>`