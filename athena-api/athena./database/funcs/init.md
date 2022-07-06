---
description: Athena.database.funcs.init
---

# init

Used to initialize a database with a MongoDB connection URI and an array of collections (tables).

It creates a single Database instance.

{% hint style="danger" %}
This should **NEVER** be used as Athena already sets up your Database and creates a connection to your Database if configured correctly. This is just for documentation purposes only.
{% endhint %}

### Usage

Arguments

* url -> string
  * [https://www.mongodb.com/docs/manual/reference/connection-string/](https://www.mongodb.com/docs/manual/reference/connection-string/)
* collections -> Array\<string>
  * Example: \['vehicles', 'characters', 'accounts']

Returns

* Promise of successful connection as a boolean.

```typescript
Athena.database.funcs.init('mongodb://username:password@127.0.0.1:27017', ['data']);
```
