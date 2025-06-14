---
description: 'H2, Myql, Postgresql. Select the db that you will use with:'
---

# Database

```
//use mysql or postgresql or h2
snello.dbtype=xxxxxx
```

```
quarkus.datasource.mysql.db-kind=mysql
quarkus.datasource.mysql.username=snello
quarkus.datasource.mysql.password=snello
quarkus.datasource.mysql.jdbc.url=jdbc:mysql://localhost:3306/snello
quarkus.datasource.mysql.jdbc.min-size=1
quarkus.datasource.mysql.jdbc.max-size=5
quarkus.datasource.mysql.jdbc=true


quarkus.datasource.postgresql.db-kind=postgresql
quarkus.datasource.postgresql.username=snello
quarkus.datasource.postgresql.password=snello
quarkus.datasource.postgresql.jdbc.url=jdbc:postgresql://localhost:5432/snello
quarkus.datasource.postgresql.jdbc.min-size=1
quarkus.datasource.postgresql.jdbc.max-size=5
quarkus.datasource.postgresql.jdbc=true

quarkus.datasource.h2.db-kind=h2
quarkus.datasource.h2.username=sa
quarkus.datasource.h2.password=
quarkus.datasource.h2.jdbc.url=jdbc:h2:file:../src/main/resources/data/database;AUTO_SERVER=true;DB_CLOSE_DELAY=-1;MODE=MySQL;IGNORECASE=TRUE;DATABASE_TO_LOWER=TRUE;CASE_INSENSITIVE_IDENTIFIERS=TRUE
quarkus.datasource.h2.jdbc.min-size=1
quarkus.datasource.h2.jdbc.max-size=5
quarkus.datasource.h2.jdbc=true
```
