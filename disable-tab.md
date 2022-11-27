---
order: b
title: Disabling a Vanilla/Mod Tab
---
To disable a tab, create a file named `disabled_tabs.json` inside your resource pack.

This file needs to be in the same location as the files used to define custom tabs.

An example of a disabled tab file would look like this:

```json
{
  "disabled_tabs": ["brewing", "decorations"]
}
```

The file in this example, disables the "Brewing" and "Decoration" tabs.

This will completely remove the tab from the inventory, and all other tabs will be re-ordered to fill the empty slots.

Items from disabled tabs still show up in the Search Tab.

!!! danger
The only tab that cannot be disabled for safety reasons, is the "Survival Inventory" tab and Custom Creative Tabs.
!!!

***

## Finding the name of tabs

Finding the name of the tab you wish to disable is simple.

While in the game, execute the command `/mct showTabNames true`. When opening your creative inventory, you will see the tiles of the tab changed. This is the value you put inside the disabled tabs file.

To enable the normal titles again, simply do `/mct showTabNames false`.
