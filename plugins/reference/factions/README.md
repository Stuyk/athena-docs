---
description: The Factions Plugin
---

# Factions

### Abstract

The faction system is a grouping system for admins to help player's group people together. It can be used for gangs, factions, businesses, etc. The current iteration of Factions **does not** have any built-in factions. You will have to create them yourself.

There is already built-in group management, rank management, bank management, etc.

{% hint style="warning" %}
Currently the Faction Administrative tools are very limited. It's heavily database based.
{% endhint %}

{% content-ref url="features.md" %}
[features.md](features.md)
{% endcontent-ref %}

### Configuration

The current configuration for factions is confusing and will be rather difficult. In the near future it will hopefully be resolved but I can at least state how to handle factions a bit better.

{% hint style="warning" %}
When you modify a faction in a database you **must** restart the server.
{% endhint %}

See the sidebar for Configuration sections.

{% content-ref url="config/purchasable-vehicles.md" %}
[purchasable-vehicles.md](config/purchasable-vehicles.md)
{% endcontent-ref %}

### Usage

An admin can create a faction by doing `/fcreate faction_name_here`.

An faction owner can invite others by performing `/finvite ingame_id_here`.

A player can accept an invite by typing `/faccept`.

A player in a faction can open the panel by typing `/fopen`.

An admin may join another faction by doing `/fjoin faction_uid_here`.

An admin may overwrite faction ownership by joinig a faction and performing `/fsetowner ingame_id_here`.

### Commands

#### fcreate

This command can be used to create a faction as an Admin.

Requires the admin to not be in a faction already.

{% tabs %}
{% tab title="Usage" %}
```
/fcreate [faction_name]
```
{% endtab %}

{% tab title="Example" %}
```
/fcreate Vilachi Crime Family
```
{% endtab %}
{% endtabs %}

#### fopen

Opens a faction panel if the player is in a faction.

{% tabs %}
{% tab title="Usage" %}
```
/fopen
```
{% endtab %}
{% endtabs %}

#### fjoin

Forces the admin to quit their current faction and join a new faction by uid.

{% tabs %}
{% tab title="Usage" %}
```
/fjoin [uid]
```
{% endtab %}

{% tab title="Example" %}
```
/fjoin 626334499dba0683985d65ea
```
{% endtab %}
{% endtabs %}

#### finvite

Invite a player to your faction if you have invite permissions.

{% tabs %}
{% tab title="Usage" %}
```
/finvite [id_or_first_las]
```
{% endtab %}

{% tab title="Example" %}
```
/finvite 5
```
{% endtab %}
{% endtabs %}

#### faccept

Accept last invite.

{% tabs %}
{% tab title="Usage" %}
```
/faccept
```
{% endtab %}
{% endtabs %}

#### fsetowner

As an admin override the current owner of the faction to another player in-game in the faction.

{% tabs %}
{% tab title="Usage" %}
```
/fsetowner [id]
```
{% endtab %}

{% tab title="Example" %}
```
/fsetowner 5
```
{% endtab %}
{% endtabs %}
