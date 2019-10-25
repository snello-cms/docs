---
description: File System or S3
---

# Storage

using **fs** \(file system\):

```text
environment:
        MICRONAUT_STORAGE_TYPE: fs
        MICRONAUT_ROUTER.STATIC-RESOURCES_FILES_PATHS: /xxx/yyy

```

using **s3** \(object storage aws compliant\) 

```text
environment:
        MICRONAUT_STORAGE_TYPE: s3
        MICRONAUT_S3_ENDPOINT: https://xxxxx.minio.io
        MICRONAUT_S3_ACCESSKEY: accesskey
        MICRONAUT_S3_SECRETKEY: password
        MICRONAUT_S3_BUCKETNAME: bucket_name
        MICRONAUT_S3_REGION: us-east-1
```



