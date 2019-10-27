---
description: >-
  When you add to your metadata a multijoin field, snello will create for you a
  lot of things.
---

# Multijoin: database and rest queries

To understand the snello behavior, we will use an example.

* [ ] create two metadata
  * [ ] create courses
  * [ ] create students
* [ ] snello magic creations
* [ ] query with rest api

### 1\) create a "courses" metadata

* uuid \[uuid - slug on name\]
* name \[string\]
* description \[text - tinymce\]

### 2\) create a "students" metadata

* uuid \[uuid - slug on surname\]
* name \[string\]
* surname \[string\]
* courses  \[multijoin -&gt; courses\]

