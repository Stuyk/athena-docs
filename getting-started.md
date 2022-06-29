---
description: How to start working with the Athena Roleplay Framework.
---

# Getting Started

### Full Installation

It is recommended to do a full install but quick instructions are provided below.

{% content-ref url="installation/installing-on-windows.md" %}
[installing-on-windows.md](installation/installing-on-windows.md)
{% endcontent-ref %}

{% content-ref url="installation/installing-on-linux.md" %}
[installing-on-linux.md](installation/installing-on-linux.md)
{% endcontent-ref %}

### Fast Installation

If you wish to use Athena but not make any changes to the core (unlikely you won't make changes) here are some simple instructions for the every day developer who just wants to test this with the alt:V Client quickly.

#### Windows

* [Install MongoDB Server](https://www.mongodb.com/try/download/community)
* [Install Git](https://git-scm.com/downloads)
* [NodeJS 17+](https://nodejs.org/en/download/)
* [alt:V Client](https://altv.mp/)

#### Run Commands in Terminal, PowerShell, or a CLI

{% tabs %}
{% tab title="Step 1" %}
```
git clone https://github.com/Stuyk/altv-athena
```
{% endtab %}

{% tab title="Step 2" %}
```
cd altv-athena
```
{% endtab %}

{% tab title="Step 3" %}
```
npm install
```
{% endtab %}

{% tab title="Step 4" %}
```
npm run update
```
{% endtab %}

{% tab title="Step 5" %}
```
npm run windows
```
{% endtab %}

{% tab title="Step 6" %}
* Launch the alt:V Client
* Join with`0.0.0.0:7788` in Direct Connect
  * If the above does not work, try `127.0.0.1:7788`
* That's it.
{% endtab %}
{% endtabs %}
