---
description: The unique identify of your rows
---

# UUIDs

_**uuid:**_  
`550e8400-e29b-41d4-a716-446655440000`

_**slug:**_

```text
https://yoast.com/slug/
```

A slug is the part of a URL which identifies a particular page on a website in an easy to read form. In other words, it’s the part of the URL that explains the page’s content. For this article, for example, the URL is [https://yoast.com/slug](https://yoast.com/slug), and the slug simply is ‘slug’.

```text
To create a slug, you should declare another field name, 
that we will use to "slug it". 
```

The slug generator function:

```text
field.trim().replaceAll("[^a-zA-Z0-9\\s]", "").replaceAll("[\\s]", "-");
```

 We also assure witch the generated uuid is unique.

_**autoincrement:**_

traditional sequence or identity

