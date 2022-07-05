---
description: General information about how to use the API while programming.
---

# About API

Athena itself has a simple API that can be accessed based on where you are writing your code.

### Difference Between Server & Client

The server-side API is where you manage a player's data to reflect changes that will be pushed to client-side. For example when you add $5 in currency to a player, it gets saved in a server-side database, and then that data is synchronized over to the player.

Examples of Server and Client

* Client-side is where you display text on a screen for a specific player.
* Client-side is where you create Web Views to show to that specific player.
* Server-side is where you currency is modified and saved to a database.
* Server-side is where a vehicle is created.
* Server-side is where a Dealership determines if you have enough money to purchase a vehicle, add it to the player, and then save that data to the database.

### Server API

This API can specifically be accessed by simply writing... `Athena`. Which will give you various options available on the server-side such as:

* database
* controllers
* extensions
* injections
* player
* systems
* vehicle
* views
* webview
* utility

### Client API

&#x20;This API can specifically be accessed by writing... `AthenaClient`. Which will give you various options on client-side such as...

* sound
* webview
* utility
