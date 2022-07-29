---
description: Athena.controllers.admin.unbanPlayer
---

# unbanPlayer

Used to unban a player from the server.

### Usage

Arguments

* discord -> string
  * The discord ID of the player to unban.
  * Example: '202685967935471617'

Returns

* Promise to return a boolean. True if the player was unbanned, false if not.

```typescript
Athena.controllers.admin.unbanPlayer('202685967935471617');
```
