---
title: "Migrating from V2"
---

Simple Discord Link 3.0.0+ are not a drop-in upgrade for 2.+. You will need to make some changes to both your server, and the config to get V3 to work.

To upgrade to V3, you will have to let the mod generate a new config file for you, and copy the values over.

### Server Side Changes for V3

* You can remove the `sdlinkwhitelist.db` file, unless you plan on going back to V2

### Mod Changes for V3

* V3 doesn't use Whitelisting/Account Linking as separate systems anymore. They are now combined into a single, easy to use [Access Control](./features/whitelisting.md) system. Players will that were verified on V2, will need to reverify their account on V3.
* Everything else you should be able to copy over from your config.
* The config file has moved to `config/simple-discord-link/simple-discord-link.toml`