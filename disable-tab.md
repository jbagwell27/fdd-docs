---
order: b
title: Disabling a Vanilla/Mod Tab
---
To completely disable the content of a tab (Not hide it, sadly, but only hide the contents), you need to create a file called `disabled_tabs.json` inside your resource/datapack.

This file needs to be in the same location as the files used to define custom tabs.

An example of a disabled tab file would look like this:

```json
{
  "disabled_tabs": ["brewing", "decorations"]
}
```

The file in this example, disables the "Brewing" and "Decoration" tabs.

***

## Finding the name of tabs

Finding the name of the tab you wish to disable is simple.

While in the game, execute the command `/mct showTabNames true`. When opening your creative inventory, you will see the tiles of the tab changed. This is the value you put inside the disabled tabs file.

To enable the normal titles again, simply do `/mct showTabNames false`.
