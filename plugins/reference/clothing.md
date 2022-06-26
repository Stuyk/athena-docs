---
description: Athena's Default Clothing Shops
---

# Clothing

### Abstract

The clothing plugin creates multiple clothing shops across the map. They all act the same. They allow the player to customize their clothing and combine different components to create their ideal outfit. All items are separated on purchase, and are not auto-equipped on purchase.

📁 `src/core/plugins/core-clothing/`

It allows the player to do the following:

* Select Hat
* Select Shirt
* Select Pants
* Select Bags
* Select Accessories
* etc.

It also includes a standard interface to go with it.

![Standard Clothing Shop Interface](https://i.imgur.com/IkntRRE.png)

### Configuration

The configuration can be found in the following folder:

📁 `src/core/plugins/core-clothing/shared/config.ts`

* MAXIMUM\_COMPONENT\_VALUES
  * The maximum number of GTA:V components available per sex, per type.
  * These should almost **never** be adjusted.
  * They will be adjusted when GTA:V introduces new DLC Packs.
* MAXIMUM\_PROP\_VALUES
  * The maximum number of GTA:V props available per sex, per type.
  * These should almost **never** be adjusted.
  * They will be adjusted when GTA:V introduces new DLC Packs.
* DLC\_CLOTHING
  * These should only be adjusted when you have clothing mods.
  * Best to look at the following page:
* DLC\_PROPS
  * Same as above. Check the `Adding Clothes` section for mods.

{% content-ref url="../../mods/adding-clothes.md" %}
[adding-clothes.md](../../mods/adding-clothes.md)
{% endcontent-ref %}

_The camera is created based on the player's position and heading._

### Usage

A player can find a `t-shirt` icon on their map. They can physically visit the location and press `E` to open the interface for the clothing shop.

### Commands

No Commands Available
