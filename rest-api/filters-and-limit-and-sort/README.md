---
description: How to use query params to get alla data.
---

# filters & limit & sort

{% hint style="info" %}
### filters
{% endhint %}

To use **filters** you need to add to all field the postfix.

Immagine that you have a metadata named "users":

* uuid
* name \[string]
* surname \[string]
* age \[number]
* year \[select with values "first", "second", "third", "quarter", "fifth"]

{% hint style="info" %}
#### string comparation
{% endhint %}

**equal**

```
/api/example?year=first
```

#### not equal

```
/api/example?year_ne=first
```

**like or right like or left like or contains or not contains**

```
/api/example?year_like=fir
/api/example?year_ilike=fir // for postgresql case insensitive ilke
/api/example?year_rlike=fi
/api/example?year_llike=st
/api/example?year_contains=rs
/api/example?year_ncontains=z
```

#### in

```
/api/example?year_in=first,second
```

#### is not null or is not null or not empty or is empty

```
/api/example?year_nn
/api/example?year_inn
/api/example?year_nie
/api/example?year_ie
```

{% hint style="info" %}
#### numeric comparation
{% endhint %}

### less than or less than equal

```
/api/example?age_lt=18
/api/example?age_lte=18
```

### grether than or less than equal

```
/api/example?age_gt=18
/api/example?age_gte=18
```

{% hint style="info" %}
**order by**
{% endhint %}

```
/api/example?_sort=name
```

### start

```
/api/example?_start=1
```

### limit

```
/api/example?_limit=2
```

### select fields �

```
/api/example?select_fields=name,surname
```

�
