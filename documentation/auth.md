# Authentication API (Gateway)

>  **Used as the gateway for reach graphql Endpoints, provide jwt and session based authentication.**

## /auth

#### POST [/auth/jwt]

> Authenticate returning a valid JWT token.
``` 
Example :
{
  username: 'allan.murara@gmail.com',
  password: '1234'
}
```

### Auth Parameters 
| Attribute | Type | Required | Description |
| --------- | ---- | -------- | ----------- |
| `authorization` | header | no | JWT Token  |

### Parameters
| Attribute | Type | Required | Description |
| --------- | ---- | -------- | ----------- |
| `username` | string | yes | Should provide valid user email |
| `password` | string | yes | User password|

### Response
```
status: 200 OK
{
  token: 'validtokenjson'
}
```
##

#### POST [/auth/session]

> Authenticate and generate a valid session.
``` 
Example :
{
  username: 'allan.murara@gmail.com',
  password: '1234'
}
```

### Auth Parameters 
| Attribute | Type | Required | Description |
| --------- | ---- | -------- | ----------- |
| `authorization` | header | no | JWT Token  |

### Parameters
| Attribute | Type | Required | Description |
| --------- | ---- | -------- | ----------- |
| `username` | string | yes | Should provide valid user email |
| `password` | string | yes | User password|

### Response
```
status: 200 OK
{
    logged:  true
}
```
##

#### POST [/auth/signout]

> Sign Out. Exclusive for Session based authentications. (JWT Tokens keep valid even after signout)


### Auth Parameters 
| Attribute | Type | Required | Description |
| --------- | ---- | -------- | ----------- |
| `authorization` | header | no | JWT Token  |


### Response
```
status: 200 OK
{
  loggedOut: true
}
```
##
