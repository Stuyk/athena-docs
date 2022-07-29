---
description: AthenaClient.sound.playFromEntity
---

# playFromEntity

Used to play a 3D sound comming from an entity using the audio webview.
{% hint style="info" %}
Does not update after first play. So if the entity has moved, the sound will not move.
{% endhint %}
Audios are found and can be added in `src-webviews/public/assets/sounds`

### Usage

Arguments

* entity -> alt.Entity
  * The entity to play the sound from
* soundName -> string
  * Name of the audio file
  * Example: 'unlock.ogg'

Returns

* Returns a void.

```typescript
AthenaClient.sound.playFromEntity(targetPlayer, 'unlock.ogg');
```
