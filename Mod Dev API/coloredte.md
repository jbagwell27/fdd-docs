---
order: d
title: Adding a colored Light (TileEntity)
---
Adding a Tile Entity that produces colored lighting is also really easy.

You can register the Tile Entity in a dedicated class file like `ColoredLightRegistrationHandler` or from within your item constructors. The guide below contains an example for both.

## Using a dedicated class
Create a file inside your mod that you can call anything you want.

Add something similar to the code below:
```java
package my.package.name;

import blah.blah.blah;

public class ColoredLightRegistrationHandler {

   public static void initRegistries() {
        // Colored Light Tile Entity's
        if (ModList.get().isLoaded("rgblib")) {
            ColoredLightManager.registerProvider(RegistryHandler.TE_NAME.get(), RegistryHandler.TE_NAME.get()::yourColoredLightEventName);
        }
   }
}
```
So explanation of the code. `RegistryHandler.TE_NAME.get()` gets the actual Tile Entity class from your Registry handler. `RegistryHandler.TE_NAME.get()::yourColoredLightEvent` refers to the actual method inside your Tile Entity class that handles the colored lighting. Remember to call `initRegistries()` after your mod has been set up. Please note that this code is CLIENT SIDE ONLY!

## Inside the TileEntity constructor
To register the Tile Entity from inside the constructor, your code will look something like this:
```java
package my.package.name;

import blah.blah.blah;

public class MyTE extends TileEntity {

   public MyTE() {
        // Colored Light Tile Entity
        if (ModList.get().isLoaded("hypcore")) {
            ColoredLightManager.registerProvider(this, this::yourColoredLightEventName);
        }
   }
}
```

## Colored Light Method
Your Colored Light method will look something like this:
```java
public RGBLight yourColoredLightEvent(TileEntity te, BlockPos pos) {
   return RGBLight.builder().position(pos).color(1.0f, 0f, 0f).radius(14).build();
}
```
The code above produces a Red Light with a radius of 14 (similar to the light reach of a torch). Your method can be called anything, as long as it is passed correctly to the registration code.

!!!warning
DO NOT MAKE THIS METHOD STATIC OR TILEENTITIES OF THE SAME KIND WILL HAVE THE SAME LIGHT AT ALL TIMES!
!!!

And that's it! It's as simple as that. Keep in mind that this mod is designed in such a way that it is optional, which mean, people can still use your mod without RGBLib installed.
