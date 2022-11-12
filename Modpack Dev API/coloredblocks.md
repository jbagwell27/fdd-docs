---
order: a
title: Adding a colored Lights (Blocks)
---
RGBLib includes a JSON api that modpack makers/players can use to add their own colored lighting.

They are added using JSON files. You can add them as part of a resource pack, inside a mod, or using the dedicated folder. Once you launch the game for the first time, you will find a folder called `coloredlights` inside your game directory. Here you can place the needed JSON files.

If you are doing this inside a resource pack, your setup will look something like this:
```
assets/rgblib/coloredlights

OR

assets/minecraft/coloredlights
```

You can then place your `blocks.json` file inside these folders.

For mod devs, you simply add the following folders:
```
assets/modid/coloredlights
```
You can then place your `blocks.json` file inside the folder.

!!!warning
When making changes, you can apply them without restarting the game. Simply press `INSERT` to open the RGBLib config GUI and press Reload JSON Lights, or if you don't have `ClothConfig` installed, just press `INSERT`
!!!

For blocks, your file needs to be called `blocks.json`. Below is a sample JSON file with comments:
```json
{
  "enabled": true, // Enables Block lighting
  "lights": [ // List of blocks to light up with
    {
      "name": "minecraft:redstone_lamp", // The ingame name of the block. This will be modid:blockname
      "r": 255, // Red value of the light
      "g": 255, // Green value of the light
      "b": 255, // Blue value of the light
      "radius": 14, // The radius of the light
      "state": { // The state the block must be in to emit colored light
        "property": "lit", // State name (LIT, POWERED, LEVEL etc)
        "value": "true" // Value the state must be in (lit=true, powered=true, level=15 etc)
      }
    },
    {
      "name": "minecraft:redstone_wire",
      "r": 255,
      "g": 0,
      "b": 0,
      "radius": 5,
      "state": {
        "property": "power",
        "value": "15"
      }
    },
    {
      "name": "minecraft:torch",
      "r": 255,
      "g": 255,
      "b": 255,
      "radius": 14,
      "state": {
        "property": "", // Leave this blank to always emit light regardless of the block state
        "value": "" // Leave this blank to always emit light regardless of the block state
      }
    }
  ]
}
```
!!!info
You can find more examples here: [Preset Packs](https://github.com/hypherionmc/hyperlighting_core/tree/master/presetpacks)
!!!

!!!warning
Please note that in the case of a block being defined in multiple files (For example inside a mod and a resource pack), the last loaded one will be used. A block using the JAVA api from RGBLib, will be ignored
!!!
