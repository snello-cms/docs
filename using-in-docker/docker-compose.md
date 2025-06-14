---
description: 'Example of complete docker-compose:'
---

# Docker compose

snello docker-compose.yml

```
services:
  snello-api:
    restart: always
    image: snellocms/snello-api-quarkus:5.0.0
    environment:
      SNELLO_DBTYPE: postgresql
      QUARKUS_DATASOURCE_POSTGRESQL_USERNAME: user
      QUARKUS_DATASOURCE_POSTGRESQL_PASSWORD: password
      QUARKUS_DATASOURCE_POSTGRESQL_JDBC_URL: jdbc:postgresql://postgres:5432/snello
      QUARKUS_MINIO_HOST: minio
      QUARKUS_MINIO_PORT: 9000
      QUARKUS_MINIO_SECURE: false
      QUARKUS_MINIO_ACCESS_KEY: minio@xxx.it
      QUARKUS_MINIO_SECRET_KEY: xxxxxxxxx
      SNELLO_STORAGETYPE: s3
      SNELLO_S3_FOLDER: inline_help
      SNELLO_S3_BUCKETNAME: snello
      QUARKUS_OIDC_AUTH_SERVER_URL: https://sso.xxx.it/realms/xxxx
      QUARKUS_OIDC_CLIENT_ID: snello-api
      TZ: "Europe/Rome"
    labels:
      - "traefik.backend=snello-api"
      - "traefik.enable=true"
      - "traefik.frontend.rule=Host:kayak.love;PathPrefix:/api;"
      - "traefik.frontend.priority=80"
      - "traefik.docker.network=web"
      - "traefik.port=8080"
      - "com.centurylinklabs.watchtower.enable=true"
    networks:
      - web
  snello-admin:
    restart: always
    image: snellocms/snello-admin:3.0.0
    volumes:
      - ./config-snello-admin.json:/usr/share/nginx/html/snello-admin/assets/config.json
    depends_on:
      - snello-api
    labels:
      - "traefik.backend=snello-admin"
      - "traefik.enable=true"
      - "traefik.frontend.rule=Host:kayak.love;PathPrefix:/snello-admin;"
      - "traefik.frontend.priority=50"
      - "traefik.docker.network=web"
      - "com.centurylinklabs.watchtower.enable=true"
    networks:
      - web
networks:
  web:
    external: true
```
