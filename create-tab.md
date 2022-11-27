---
order: a
title: Create a Custom Tab
---
Creating or configuring a custom tab, is done through JSON through a Resource pack.

!!!warning
~~When making changes to the resource or data pack, you will need to restart the game in order to view those changes. This is due to the way the tabs are created!~~

You can now reload edited tabs by running the `/mct reloadTabs` command. Available since 1.1

To reload Language files, you need to use the standard `F3 + T` key combo

!!!
!!!info
You can define multiple tabs inside a single pack. You do not need to create a pack for each one
!!!

***

### Getting Started
The first thing you want to do is, create a new, empty resource pack. To save you some time, you can also download the [SKELETON PACK](https://cdn.firstdarkdev.xyz/curse/mct/dl/skeleton_pack_v2.zip) with all the base files already created.

`Other Downloads`

[!button variant="danger" text="Old Format (1.18)"](https://cdn.firstdarkdev.xyz/curse/mct/dl/skeleton_pack.zip) [!button variant="success" text="New Format (1.18)"](https://cdn.firstdarkdev.xyz/curse/mct/dl/skeleton_pack_v2.zip) [!button variant="warning" text="New Format (1.19+)"](https://cdn.firstdarkdev.xyz/curse/mct/dl/skeleton_pack_19_v2.zip)

Inside your resource pack, you will need the following folder layout:

```
|-- Pack Folder
    |-- assets
        |-- minecraft
            |-- lang
                |-- en_us.json
            |-- morecreativetabs
                |-- my_tab.json
    |-- pack.mcmeta
``` 

!!!info
When using the [SKELETON PACK](https://cdn.firstdarkdev.xyz/curse/mct/dl/skeleton_pack_v2.zip), these files/folders will already be created for you
!!!

---

### Creating your first tab
To create a new creative tab, create a file inside the `morecreativetabs` folder. You can call this `whateveryouwant.json`. This file will tell the mod how to configure the creative tab.

You will also need a lang file inside the `lang` folder. For this example, we will use `en_us.json` which is the english version of the tab names.

Below is a sample config file, with an explanation at the bottom:

```json
{
  "tab_enabled": true,
  "tab_name": "test_tab",
  "tab_stack": { "name": "minecraft:light", "nbt": "{BlockStateTag: {level:\"4\"}}"},
  "tab_items": [
    {
      "name": "minecraft:light",
      "hide_old_tab": true,
      "nbt": "{BlockStateTag: {level:\"10\"}}"
    },
    {
      "name": "minecraft:torch"
    },
    {
      "name": "minecraft:soul_torch",
      "nbt": "{customName: \"Oi Govener!\"}"
    },
    {
      "name": "minecraft:candle"
    }
  ]
}

```

Explanation:

| Item/Variable              | Purpose                                                                                                                                                                                     |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| "tab_enabled"              | Should this custom tab be loaded by the mod                                                                                                                                                 |
| "tab_name"                 | The translation key used in the `lang` file. For example: `lighting_tab`. This will be prefixed with `morecreativetabs.` So `lighting_tab` will become `morecreativetabs.lighting_tab`      |
| "tab_stack"                | The registry name and optional NBT of the item to use as the tab icon. See example above |                                                                                                   |
|                            |                                                                                                                                                                                             |
| "tab_items"                | This contains a reference to all the items contained in the tab                                                                                                                             |
| "name"                     | The registry name of the item to use as the tab icon. This must always be in format `modid:itemname`. You can find this by dropping an item on the ground and looking at it, with F3 active |
| "hide_old_tab" -> Optional | When present and enabled, the item will be removed from its original tab, and only be shown in the custom tab                                                                               |
| "nbt" -> Optional          | Pretty self explanatory, but this allows you to set NBT values on an item inside the tab                                                                                                    |

!!!warning
"tab_enabled", "tab_name", "tab_stack" and "tab_items" must always be present, or the file will not load
!!!

---

### Changing the name of an item

Since V1.1, you can now override the name of an item in a custom tag. To do this, add the following to your NBT tag:

```
customName: \"Your Custom Name Here\"
```

---

### More examples

Here you can download a couple of pre-made packs, to see how they work and make your own from them.

* [Disable Brewing](https://cdn.firstdarkdev.xyz/curse/mct/dl/disable_brewing.zip) -> Disables the Brewing Tab
* [Disable Brewing (1.19+)](https://cdn.firstdarkdev.xyz/curse/mct/dl/disable_brewing_v2.zip) -> (For 1.19+) Disables the Brewing Tab
* [Amended (1.18+)](https://modrinth.com/resourcepack/amended) -> A community made pack that brings the 1.19.3/1.20 inventory to older versions
* [Dev Pack (1.19+)](https://cdn.firstdarkdev.xyz/curse/mct/dl/devpack.zip) -> (For 1.19+) This is the test resource pack we use while developing the mod
