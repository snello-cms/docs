---
description: >-
  The idea in "links" is define relationship between data in same table. For
  example if you want create a join between news (italian and english version).
---

# Links

```
    name: string;
    labels: string;
    metadata_name: string;
    metadata_key: string;
    metadata_searchable_field: string;
    metadata_lock_field: string;
    metadata_generated_uuid: string;
    uuid_name: string;
    created: boolean;
```

In the following block, you can find a typical usecase:

```
 
- name: languages
- labels: IT, EN, FRA, DE
- metadata_name: news
- metadata_key: news.uuid
- metadata_searchable_field: news.title
- metadata_lock_field: news.lang=label
=> verra' generata il metadato:
- metadata_generated_uuid - es languages.uuid=label
```

*
