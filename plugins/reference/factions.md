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

Below are a few screenshots to help you visualize the features.&#x20;

{% hint style="info" %}
Data may not be reflected correctly as it is a preview and does not reflect production.
{% endhint %}

{% tabs %}
{% tab title="Members " %}
![](https://i.imgur.com/IYNDD1h.png)
{% endtab %}

{% tab title="Ranks" %}
![](https://i.imgur.com/iMZIV1j.png)

![](https://i.imgur.com/0elG1vm.png)
{% endtab %}

{% tab title="Bank" %}
![](https://i.imgur.com/LJ00woP.png)
{% endtab %}

{% tab title="Vehicles" %}
![](https://i.imgur.com/uiSsC9o.png)

![](https://i.imgur.com/JnoFHPo.png)
{% endtab %}

{% tab title="Settings" %}
![](https://i.imgur.com/BGV9rM5.png)
{% endtab %}
{% endtabs %}

Features:

* Invite to Faction
* Member Management
  * Change Rank
  * Kick Member
* Rank Management
  * Create Rank
  * Rename Rank
  * Modify Rank Permissions
  * Delete Rank
* Vehicle Management
  * Add Vehicles for the Faction to Purchase
  * Spawn Vehicles by Rank
* Bank Management
  * Withdraw Faction Money
  * Deposit Faction Money
  * Claim Paychecks from Faction Money
* Settings
  * Paychecks
  * Parking Spawn Locations for Vehicles
  * Head Quarters
    * Where to create a blip to represent the Faction
* Injectable WebViews into the Faction Page
  * Basically means you can expand on the core plugin by adding new pages.
  * 📁 `src/core/plugins/core-faction-paychecks`

### Configuration

The current configuration for factions is confusing and will be rather difficult. In the near future it will hopefully be resolved but I can at least state how to handle factions a bit better.

{% hint style="warning" %}
When you modify a faction in a database you **must** restart the server.
{% endhint %}

Let's talk about some things.

#### Adding Purchaseable Vehicles

If you have a faction already created, you have to edit the database to add new vehicles. Here's how to do that.

{% tabs %}
{% tab title="Step 1" %}
Open MongoDB Compass

Connect to the Database

Go to the Factions Collection



![](https://i.imgur.com/0fSpS7e.png)
{% endtab %}

{% tab title="Step 2" %}
Select a Faction

Expand Settings



![](https://i.imgur.com/ySQPKl9.png)
{% endtab %}

{% tab title="Step 3" %}
Create an Array in Settings

Click the `+` to add a new field. It's next to settings.



![](https://i.imgur.com/4bC2cDR.png)
{% endtab %}

{% tab title="Step 4" %}
Name the new field key `vehicles`.

Change the type to Array.



![](https://i.imgur.com/aeIe3RH.png)
{% endtab %}

{% tab title="Step 5" %}
Append a new object to the vehicles array.

It should contain a `model` and a `price`.

Add as many of these as you want.



![](https://i.imgur.com/3I5cr1n.png)

{% hint style="info" %}
Remember to hit `update` and restart your server when done.
{% endhint %}
{% endtab %}
{% endtabs %}

### Usage

An admin can create a faction by doing `/fcreate faction_name_here`.

An faction owner can invite others by performing `/finvite ingame_id_here`.

A player can accept an invite by typing `/faccept`.

A player in a faction can open the panel by typing `/fopen`.

An admin may join another faction by doing `/fjoin faction_uid_here`.

An admin may overwrite faction ownership by joinig a faction and performing `/fsetowner ingame_id_here`.

### Commands

