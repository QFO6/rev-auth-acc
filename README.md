# Revel auth module via Access Control Center(ACC) service

# Usage:

## Installation

Install module

```
# specific version
go get go get github.com/QFO6/rev-auth-acc@vx.x.x
# or get latest
go get github.com/QFO6/rev-auth-acc@master
```

## Setup

Include module in app.conf

```
module.revauthacc=github.com/QFO6/rev-auth-acc
```

Include module in conf/routes

```
module:revauthacc
```

Needs to define routes in under your revel_app/conf/routes file

```
GET    /logout                                          Auth.Logout
POST   /logout                                          Auth.Logout
POST   /login                                           Auth.Authenticate
```

Add revel config variables to your_revel_app/conf/app.conf file

```
auth.connect = ${auth_connect}
```

Inject env variables during startup or deployment

```
export auth_connect="https://acc.test.com/api/service/auth"
```

