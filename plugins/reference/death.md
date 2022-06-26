---
description: The core death plugin in the Athena Framework
---

# Death

### Abstract

The death plugin simply allows the player to choose when they want to revive. It's simply command based, and will prompt the user to type the command once a re-spawn timer is exhausted.

📁 `src/core/plugins/core-death/`

Current Features

* Respawn at Hospital
* Ragdoll on Death
* Command to Invoke re-spawn after Timer
* A very simple death screen

{% embed url="https://gfycat.com/lividdetailedkomododragon" %}

### Configuration

The default death configuration can be found here:

📁 `src/core/plugins/core-death/server/src/config.ts`

* RESPAWN\_TIME
  * Time in milliseconds before a player my type `/acceptdeath`.
* LOSE\_ALL\_WEAPONS\_ON\_RESPAWN
  * Self explanatory.
* RESPAWN\_HEALTH
  * The health to give the player when they respawn. `100-199`.
* RESPAWN\_ARMOUR
  * The armour to give the player when they respawn.
* HOSPITALS
  * An array of Vector3 positions where they can respawn.

### Usage

When a player dies it triggers the dead state.

The death state also invokes a meta change client-side and on server-side.

{% tabs %}
{% tab title="Server" %}
```
player.data.isDead
```
{% endtab %}

{% tab title="Client" %}
```
alt.Player.local.meta.isDead
```
{% endtab %}
{% endtabs %}

After the change is invoked. A timer is started and updated frequently until the player's timer hits zero. After zero a player may type `/accpetdeath` to fully revive at a hospital.

A hospital is determined by closest to the dead player.

### Commands

#### revive

An administrative command to revive a player.

If an id is **not defined** it will revive self.

{% tabs %}
{% tab title="Usage" %}
```
/revive [ingame_player_id]
```
{% endtab %}

{% tab title="Example" %}
```
/revive 5
```
{% endtab %}
{% endtabs %}

#### acceptdeath

A player command that will allow a player to re-spawn after some time.

Alternative: `/respawn`

{% tabs %}
{% tab title="Usage" %}
```
/acceptdeath
```
{% endtab %}
{% endtabs %}
