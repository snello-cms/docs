---
description: Snello Api generator structure
---

# Architecture

Some basic concept

* metadata
  * field definitions
* select queries
* conditions

Using the REST api, you write your data in the database:

actually h2, mysql, postgresql.

The Admin application give you the way to control the flux of data.

The api and the admin are decoupled.

Api without admin? YES you CAN!

Deploy the api server on a server and the admin server in a separate server? YES you CAN!

