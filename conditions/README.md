---
description: The conditions aree the best way to define "custom queries".
---

# Conditions

## Parameter conditions

You should define the conditions that will bypass the normal queries on metadata table. The conditions can be applied on different parameters in "and " or "or" combination.

You must define the **metadata\_name** \(the table that will be queried\).

You can apply the **condition** that should be verified on parameters in some way:

* \_nn \(not null\)
* \_nie \(not empty\)
* \_gt \(greater than\)
* \_gte \(greater equal than\)
* \_lt \(lower than\)
* \_lte \(lower equal than\)

And you can mix the conditions using "&&" or "\|\|".

```text
studenti_id_gt = 20 && studenti_id_lt = 30
studenti_id_nn && join_table_nn
```

The **query\_params** that will be used for the sql query

```
query_params: "studenti_id" 
```

The **sub\_query** to concatenate after **where** in the sql query:

```
sub_query: "uuid in (
select classi_id from studenti_classi where studenti_id = ?
)" 
```

You can define a "separator" to concatenate more conditions.

A complete example:

```
metadata_name: "classi", 
condition: "studenti_id_nn && join_table_nn" 
metadata_name: "classi" 
query_params: "studenti_id" 
sub_query: "uuid in (select classi_id from studenti_classi 
where studenti_id = ?)"
```



