---
description: it's quarkus style with keycloak!
---

# Authentication & Authorization

```
quarkus.http.auth.permission.roles1.policy=role-policy1
quarkus.http.auth.permission.roles1.paths=/api/*
quarkus.http.auth.permission.roles1.methods=POST,PUT,DELETE,PATCH

quarkus.http.auth.permission.permit1.paths=/api/*
quarkus.http.auth.permission.permit1.policy=permit
quarkus.http.auth.permission.permit1.methods=OPTIONS,GET
```
