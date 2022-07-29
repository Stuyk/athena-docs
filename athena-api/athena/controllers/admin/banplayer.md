---
description: Athena.controllers.admin.banPlayer
---

# banPlayer

Used to ban a player from the server.

### Usage

Arguments

* player -> alt.Player
* reason -> string

Returns

* Promise to return a boolean. True if the player was banned, false if not.

```typescript
Athena.controllers.admin.banPlayer(player, "Cheating");
```
