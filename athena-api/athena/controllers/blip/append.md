---
description: Athena.controllers.blip.append
---

# append

Adds a global blip the player loads when they join.
Also appends it to any online players.
{% hint style='info' %}
Requires a UID to remove it later.
{% endhint %}


### Usage

Arguments

* blip -> Blip

Returns

* Returns a string containing the UID of the blip.

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

Athena.controllers.blip.append(newBlip);
```
