---
description: How to use query params to get alla data.
---

# filters & limit & sort

{% hint style="info" %}
## filters
{% endhint %}

To use **filters** you need to add to all field the postfix.

Immagine that you have a metadata named "users":

* uuid
* name \[string\]
* surname \[string\]
* age \[number\]
* year \[select with values "first", "second", "third", "quarter", "fifth"\]

{% hint style="info" %}
### string comparation
{% endhint %}

**equal**

```text
/api/example?year=first
```

#### not equal

```text
/api/example?year_ne=first
```

**like or right like or left like or contains or not contains**

```text
/api/example?year_like=fir
/api/example?year_rlike=fi
/api/example?year_llike=st
/api/example?year_contains=rs
/api/example?year_ncontains=z
```

#### in 

```text
/api/example?year_in=first,second
```

#### is not null or is not null or not empty or is empty

```text
/api/example?year_nn
/api/example?year_inn
/api/example?year_nie
/api/example?year_ie
```

{% hint style="info" %}
### numeric comparation
{% endhint %}

### less than or less than equal

```text
/api/example?age_lt=18
/api/example?age_lte=18
```

### grether than or less than equal

```text
/api/example?age_gt=18
/api/example?age_gte=18
```

{% hint style="info" %}
**order by**
{% endhint %}

```text
/api/example?_sort=name
```

### start

```text
/api/example?_start=1
```

### limit

```text
/api/example?_limit=2
```

### select fields  

```text
/api/example?select_fields=name,surname
```

 

