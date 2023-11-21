---
title: "Migrating from V2"
---

While SDLink V2 and V3 are "the same", you cannot directly update from V2.

To upgrade to V3, you will have to let the mod generate a new config file for you, and copy the values over.

### Server Side Changes for V3

* Disable Whitelisting. The [Access Control](./features/whitelisting.md) feature does not use the Minecraft whitelist anymore, and requires it to be disabled.
* You can remove the `sdlinkwhitelist.db` file, unless you plan on going back to V2

### Mod Changes for V3

* V3 doesn't use Whitelisting/Account Linking as separate systems anymore. They are now combined into a single, easy to use [Access Control](./features/whitelisting.md) system. Players will that were verified on V2, will need to reverify their account on V3.
* Everything else you should be able to copy over from your config.