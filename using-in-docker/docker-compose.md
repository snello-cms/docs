---
description: Example of complete docker-compose
---

# Docker compose

```text
version: '3'
services:
  pgadmin4:
    image: dpage/pgadmin4
    expose:
      - "80"
    ports:
      - '5050:80'
    environment:
       PGADMIN_DEFAULT_EMAIL: xxxx
       PGADMIN_DEFAULT_PASSWORD: xxxxx
  snello-api:
    restart: always
    image: snellocms/snello-api:latest
    ports:
      - "8080:8080"
    environment:
      JDBC_HOST: host
      JDBC_TYPE: postgresql
      JDBC_PORT: 3456
      JDBC_DB: snello
      JDBC_USERNAME: snello
      JDBC_PASSWORD: snello
      JDBC_DRIVER: org.postgresql.Driver
      MICRONAUT_DB_TYPE: postgresql
      MICRONAUT_STORAGE_TYPE: s3
      MICRONAUT_S3_ENDPOINT: https://minio.io
      MICRONAUT_S3_ACCESSKEY: xxxx
      MICRONAUT_S3_SECRETKEY: xxxx
      MICRONAUT_S3_BUCKETNAME: snello
      MICRONAUT_S3_REGION: us-east-1
      WEB_PATH: "/home/snello/files/"
      TZ: "Europe/Rome"
  minio:
    image: minio/minio
    ports:
      - "9001:9000"
    environment:
      MINIO_ACCESS_KEY: xxx
      MINIO_SECRET_KEY: xxxxx
    command: server /data
  snello-admin:
    restart: always
    image: snellocms/snello-admin:latest
    volumes:
      - ./config-snello-admin.json:/usr/share/nginx/html/snello-admin/assets/config.json
    depends_on:
      - snello-api


```

