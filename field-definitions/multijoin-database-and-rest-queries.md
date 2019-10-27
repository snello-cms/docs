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
  * Join Table Name: courses
  * Join Table Key: uuid
  * Join Table Fields: name

### 3\) snello magic: join table and condition

When you save \(in sequence\) courses and students.

* courses table
* students table
* join table: courses\_students

A "condition", to map the relationship between tables.

### 4\) rest api

* /api/courses
* /api/students
* /api/students/:id/courses

