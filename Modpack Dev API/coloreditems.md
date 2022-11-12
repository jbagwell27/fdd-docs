---
order: b
title: Adding a colored Lights (Items)
---
RGBLib includes a JSON api that modpack makers/players can use to add their own colored lighting.

They are added using JSON files. You can add them as part of a resource pack, inside a mod, or using the dedicated folder. Once you launch the game for the first time, you will find a folder called `coloredlights` inside your game directory. Here you can place the needed JSON files.

If you are doing this inside a resource pack, your setup will look something like this:
```
assets/rgblib/coloredlights

OR

assets/minecraft/coloredlights
```

You can then place your `items.json` file inside these folders.

For mod devs, you simply add the following folders:
```
assets/modid/coloredlights
```
You can then place your `items.json` file inside the folder.

!!!warning
When making changes, you can apply them without restarting the game. Simply press `INSERT` to open the RGBLib config GUI and press Reload JSON Lights, or if you don't have `ClothConfig` installed, just press `INSERT`
!!!

For blocks, your file needs to be called `items.json`. Below is a sample JSON file with comments:
```json
{
  "enabled": true, // Enables Item lighting
  "lights": [ // List of Items to light up with
    {
      "name": "minecraft:torch", // The ingame name of the item. This will be modid:blockname
      "r": 255, // Red value of the light
      "g": 255, // Green value of the light
      "b": 255, // Blue value of the light
      "radius": 14 // The radius of the light
    },
    {
      "name": "minecraft:redstone_torch",
      "r": 144,
      "g": 0,
      "b": 0,
      "radius": 8
    }
  ]
}
```
!!!info
You can find more examples here: [Preset Packs](https://github.com/hypherionmc/hyperlighting_core/tree/master/presetpacks)
!!!

!!!warning
Please note that in the case of an item being defined in multiple files (For example inside a mod and a resource pack), the last loaded one will be used. An Item using the JAVA api from RGBLib, will be ignored
!!!
