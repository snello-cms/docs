---
description: You can create all select queries.
---

# Select Queries

Give a name \(**query\_name**\), define your "**select\_query**" and finally specify if your query will use the parameters in condition \("**with\_params**"\). 

Tipically use case is create distinct query.

```text
  query_name: 'cities'
  select_query: 'select distinct(city) from users'
  with_params: 'false'
```

 

