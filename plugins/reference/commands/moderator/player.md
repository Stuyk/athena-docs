---
description: Administrative Commands against Players
---

# Player

### sethealth

Used to set a target player's health.

Health ranges from 99 - 199. 99 = Death

Don't ask, it's just GTA:V internal values.

{% tabs %}
{% tab title="Usage" %}
```
/sethealth [99-199] [player_id]
```
{% endtab %}

{% tab title="Example" %}
```
/sethealth 199 5
```
{% endtab %}
{% endtabs %}

### setarmour

Used to set a target player's armour.

Armour ranges from 0 - 100.

Don't ask, it's just GTA:V internal values.

{% tabs %}
{% tab title="Usage" %}
```
/setarmour [0-100] [player_id]
```
{% endtab %}

{% tab title="Example" %}
```
/setarmour 100 5
```
{% endtab %}
{% endtabs %}

### freeze

Used to freeze a specified player by id.

{% tabs %}
{% tab title="Usage" %}
```
/freeze [player_id]
```
{% endtab %}

{% tab title="Example" %}
```
/freeze 5
```
{% endtab %}
{% endtabs %}

### unfreeze

Used to unfreeze a specified player by id.

{% tabs %}
{% tab title="Usage" %}
```
/unfreeze [player_id]
```
{% endtab %}

{% tab title="Example" %}
```
/unfreeze 5
```


{% endtab %}
{% endtabs %}

### kick

Used to kick a player

{% tabs %}
{% tab title="Usage" %}
```
/kick [player_id] [really_long_reason_here]
```
{% endtab %}

{% tab title="Example" %}
```
/kick 5 Learn to not be hateful.
```
{% endtab %}
{% endtabs %}

### ban

Used to ban a player

{% tabs %}
{% tab title="Usage" %}
```
/ban [player_id] [really_long_reason_here]
```
{% endtab %}

{% tab title="Example" %}
```
/ban 5 Cheating
```
{% endtab %}
{% endtabs %}

### unban

Used to kick a player

{% tabs %}
{% tab title="Usage" %}
```
/unban [discord_identifier]
```
{% endtab %}

{% tab title="Example" %}
```
/unban 202685967935471617
```
{% endtab %}
{% endtabs %}

### makeadmin

Used to set a player's admin level in-game as an Admin.

Set to `0` to revoke all administrative privilege's.

{% tabs %}
{% tab title="Usage" %}
```
/makeadmin [player_id] [admin_level_number]
```
{% endtab %}

{% tab title="Example" %}
```
/makeadmin 5 4
```
{% endtab %}
{% endtabs %}

### info

Used to retrieve account information of a player in-game.

{% tabs %}
{% tab title="Usage" %}
```
/info [player_id]
```
{% endtab %}

{% tab title="Example" %}
```
/info 5
```
{% endtab %}
{% endtabs %}

