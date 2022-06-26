---
description: Administrative vehicle commands.
---

# Vehicle

### refillvehicle

Should set a vehicle's fuel to 100.

Requires the player to be inside of the vehicle.

{% tabs %}
{% tab title="Usage" %}
```
/refillvehicle
```
{% endtab %}
{% endtabs %}

### repairvehicle

Fully repairs a vehicle if the player is inside of the vehicle.

{% tabs %}
{% tab title="Usage" %}
```
/repairvehicle
```
{% endtab %}
{% endtabs %}

### tempvehicle

Spawns a temporary vehicle which despawns after exiting it.

{% tabs %}
{% tab title="Usage" %}
```
/tempvehicle [vehicle_model_hash_or_string]
```
{% endtab %}

{% tab title="Example" %}
```
/tempvehicle infernus
```
{% endtab %}
{% endtabs %}

### addvehicle

Spawns and creates a vehicle and adds it to yourself. It can be saved.

{% tabs %}
{% tab title="Usage" %}
```
/addvehicle [vehicle_model_hash_or_string]
```
{% endtab %}

{% tab title="Example" %}
```
/addvehicle infernus
```
{% endtab %}
{% endtabs %}

### setvehiclehandling

Set vehicle handling value.

Alternative: `/sh`

{% tabs %}
{% tab title="Usage" %}
```
/setvehiclehandling [tuning_key_name] [tuning_key_value]
```
{% endtab %}

{% tab title="Example" %}
```
/sh darkness 5
```
{% endtab %}
{% endtabs %}

### sessionvehicle

Create a session based vehicle. A session vehicle despawns after the server is restarted.

{% tabs %}
{% tab title="Usage" %}
```
/sessionvehicle [vehicle_model_hash_or_string]
```
{% endtab %}

{% tab title="Example" %}
```
/sessionvehicle akuma
```
{% endtab %}
{% endtabs %}

### toggleneonlights

Create a session based vehicle. A session vehicle despawns after the server is restarted.

Alternative: `/tnl`

{% tabs %}
{% tab title="Usage" %}
```
/toggleneonlights
```
{% endtab %}

{% tab title="Example" %}
```
/tnl
```
{% endtab %}
{% endtabs %}

### setneonlights

Turns neon lights on your vehicle on / off. Can toggle different positions.

Alternative: `/snl`

{% tabs %}
{% tab title="Usage" %}
```
/setneonlights [left_0-1] [right_0-1] [front_0-1] [back_0-1]
```


{% endtab %}

{% tab title="Example" %}
```
/setneonlights 1 1 0 0
```
{% endtab %}
{% endtabs %}

### fulltunevehicle

Sets entire vehicle to maximum value for all mods.

Alternative: `/ft`

{% tabs %}
{% tab title="Usage" %}
```
/fulltunevehicle
```
{% endtab %}
{% endtabs %}
