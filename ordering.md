---
order: d
title: Ordering Tabs
---

Since Version 1.2 of the mod, you can specify the order in which Creative Tabs are displayed.

To do this, you need to create a file named `ordered_tabs.json`.

### Example Layout

```json
{
  "tabs": ["morecreativetabs.test_tab", "redstone", "combat", "building_blocks", "hotbar", "search", "existing"]
}
```

As with all the other features of this mod, you need to use the Tab Name, as shown when `showTabNames` are enabled.

!!! danger Warning
When the name of a tab is missing from the `tabs` list, it will be hidden from the inventory.

Now, you obviously don't want to specify EACH AND EVERY single tab, especially in big modpacks.

So, to add in all other, non-disabled tabs, without ordering them, add an entry named `existing` to the `tabs` list.
!!!
