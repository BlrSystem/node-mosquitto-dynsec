
# node-mosquitto-dynsec

This is a NodeJS module for managing eclipse-mosquitto Dynamic Security plugin.

We added the clinetId

```js
import {MosquittoDynsec} from "mosquitto-dynsec"
const dynsec = new MosquittoDynsec()

try {
  await dynsec.connect({
    hostname: "mqtt.example.com",
    username: "foo",
    password: "bar",
    clientId: "dynamic_user"
  })
} catch(e) {
  console.error("Connect error:", e)
}

const res = await dynsec.createClient({ clientId: "dynamic_user", username: "user1", password: "pass" })
```



# Implemented commands

The folowing commands specs were imeplmented using the source code of mosquitto_ctlr as reference. (dynsec.c)

## listClients
## createClient
## deleteClient
## setClientId
## setClientPassword
## getClient
## addClientRole
## removeClientRole
## enableClient
## disableClient

## createRole
## deleteRole
## getRole
## listRoles
## addRoleACL
## removeRoleACL

## createGroup
## deleteGroup
## listGroups
## getGroup
## getAnonymousGroup
## setAnonymousGroup
## addGroupClient
## removeGroupClient
## addGroupRole
## removeGroupRole

## getDefaultACLAccess
## setDefaultACLAccess


