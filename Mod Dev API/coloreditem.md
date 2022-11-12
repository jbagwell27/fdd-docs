---
order: c
title: Adding a colored Light (Item)
---
Adding an Item that produces colored lighting is also really easy.

You can register the item in a dedicated class file like `ColoredLightRegistrationHandler` or from within your item constructors. The guide below contains an example for both.

## Using a dedicated class
Create a file inside your mod that you can call anything you want.

Add something similar to the code below:
```java
package my.package.name;

import blah.blah.blah;

public class ColoredLightRegistrationHandler {

   public static void initRegistries() {
        // Colored Light Items
        if (ModList.get().isLoaded("rgblib")) {
            ColoredLightManager.registerProvider(RegistryHandler.ITEM_NAME.get(), RegistryHandler.ITEM_NAME.get()::yourColoredLightEventName);
        }
   }
}
```
So explanation of the code. `RegistryHandler.ITEM_NAME.get()` gets the actual item class from your Registry handler. `RegistryHandler.ITEM_NAME.get()::yourColoredLightEvent` refers to the actual method inside your item class that handles the colored lighting. Remember to call `initRegistries()` after your mod has been set up. Please note that this code is CLIENT SIDE ONLY!

## Inside the Item Constructor
To register the item from inside the constructor, your code will look something like this:
```java
package my.package.name;

import blah.blah.blah;

public class MyItem extends Item {

   public MyItem() {
        // Colored Light Items
        if (ModList.get().isLoaded("rgblib")) {
            ColoredLightManager.registerProvider(this, this::yourColoredLightEventName);
        }
   }
}
```

## Colored Light Method
Your Colored Light method will look something like this:
```java
public RGBLight yourColoredLightEvent(Entity ent, ItemStack stack) {
   return RGBLight.builder().position(APIUtils.entityPos(ent)).color(1.0f, 0f, 0f).radius(14).build();
}
```
The code above produces a Red Light with a radius of 14 (similar to the light reach of a torch). Your method can be called anything, as long as it is passed correctly to the registration code.

!!!warning
DO NOT MAKE THIS METHOD STATIC OR ITEMS OF THE SAME KIND WILL HAVE THE SAME LIGHT AT ALL TIMES!
!!!

!!!info
`APIUtils` is part of the RGBLib api package
!!!

And that's it! It's as simple as that. Keep in mind that this mod is designed in such a way that it is optional, which mean, people can still use your mod without RGBLib installed.
