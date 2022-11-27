---
order: c
title: Replacing a Vanilla/Mod Tab
---

This feature allows you to replace an existing Creative Tab, with your own custom one. This is an alternative to disabling a tab.

||| First Steps
* To get started, run `/mct showTabNames true` to display the internal names of the tabs.
* Open your inventory, and click the tab you wish to replace.
* The name will now be shown as `itemGroup.modName` or `building_blocks` for vanilla tabs.

!!! danger
When naming the file, replace all instances of `.` with `_`, and replace all capital letters with lower-case letters.

For example, if the tab shows `itemGroup.modName`, it becomes `itemgroup_modname`
!!!

Now, inside your resource pack, create a file named `name_from_before.json`. 

For Example: `building_blocks.json` or `itemgroup_modname.json`
|||

---

### Example layout of a replaced Tab

In this example, we replace the `Building Blocks` tab, with a custom one.

```json
{
  "tab_enabled": true,
  "tab_name": "building_new",
  "replace": true,
  "tab_stack": { "name": "minecraft:torch" },
  "tab_items": [
    {
      "name": "minecraft:soul_torch",
      "nbt": "{customName: \"Oi Govener!\"}"
    }
  ]
}
```

Now, you will notice this layout is almost exactly the same as the layout for Custom Tabs.

But look closely, the important thing here is this: `"replace": true`

This setting, replaces the `Building Blocks` tab with the content of this one. If this setting is not present, or set to false, it will be loaded as a normal Custom Tab

---

### Example layout of a Replaced Tab, With Existing and Custom Items

In this example, we replace the `Building Blocks` tab, with a custom one, while still keeping the old items, and adding some of our own.

```json
{
  "tab_enabled": true,
  "tab_name": "building_new",
  "replace": true,
  "tab_stack": { "name": "minecraft:torch" },
  "tab_items": [
    {
      "name": "minecraft:soul_torch",
      "nbt": "{customName: \"Oi Govener!\"}"
    },
    {
      "name": "existing"
    }
  ]
}
```

Again, this file looks very similar to the previous example.

The catch here, is the addition of this:

```json
{
  "name": "existing"
}
```

This entry, is a custom entry that tells the mod, that it should add back all the items of the original tab, along with the custom items


!!! danger Notice

Please note that the following tabs cannot be replaced:

* Survival Inventory
* Search
!!!

---

### Other Examples

* [Amended (1.18+)](https://modrinth.com/resourcepack/amended) -> A community made pack that brings the 1.19.3/1.20 inventory to older versions

