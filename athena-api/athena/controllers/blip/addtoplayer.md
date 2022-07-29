---
description: Athena.controllers.blip.addToPlayer
---

# addToPlayer

Adds a blip for a specific player. So only the player can see it.
{% hint style='info' %}
Requires a UID to remove it later.
{% endhint %}

### Usage

Arguments

* player -> alt.Player
* blipData -> Blip

Returns

* Returns a void.

```typescript
const newBlip: Blip = {
    pos: { x: 0.0, y: 0.0, z: 72.0 },
    shortRange: true,
    sprite: 1,
    color: BLIP_COLOR.GREEN,
    text: 'My Blip',
    scale: 1,
    uid: 'my_test_blip',
}

Athena.controllers.blip.addToPlayer(player, newBlip);
```
