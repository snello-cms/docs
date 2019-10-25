---
description: 'H2, Myql, Postgresql'
---

# Database

with postgresql:

```text
environment:
      JDBC_HOST: postgresql
      JDBC_TYPE: postgresql
      JDBC_PORT: 5432
      JDBC_DB: snello
      JDBC_USERNAME: snello
      JDBC_PASSWORD: xxxx
      JDBC_DRIVER: org.postgresql.Driver
      MICRONAUT_DB_TYPE: postgresql
```

with mysql:

```text
environment:
      JDBC_HOST: mysql
      JDBC_TYPE: mysql
      JDBC_PORT: 3306
      JDBC_DB: snello
      JDBC_USERNAME: snello
      JDBC_PASSWORD: xxxx
      JDBC_DRIVER: com.mysql.cj.jdbc.Driver
      MICRONAUT_DB_TYPE: mysql
```

with h2:

```text
environment:
      JDBC_HOST: h2
      JDBC_TYPE: h2
      JDBC_PATH: 3306
      JDBC_DB: ./db/repository
      JDBC_USERNAME: sa
      JDBC_PASSWORD: ''
      JDBC_DRIVER: org.h2.Driver
      MICRONAUT_DB_TYPE: h2
```

