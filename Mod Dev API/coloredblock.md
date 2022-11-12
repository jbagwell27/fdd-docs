---
order: b
title: Adding a colored Light (Block)
---
Adding a block that produces colored lighting is really easy.

You can register the blocks in a dedicated class file like `ColoredLightRegistrationHandler` or from within your block constructors. The guide below contains an example for both.

## Using a dedicated class
Create a file inside your mod and call it whatever you want.

Add something similar to the code below:
```java
package my.package.name;

import blah.blah.blah;

public class ColoredLightRegistrationHandler {

   public static void initRegistries() {

        // Colored Light Blocks
        if (ModList.get().isLoaded("rgblib")) {
            ColoredLightManager.registerProvider(RegistryHandler.BLOCK_NAME.get(), RegistryHandler.BLOCK_NAME.get()::yourColoredLightEventName);
        }
   }
}
```

So explanation of the code. `RegistryHandler.BLOCK_NAME.get()` gets the actual block class from your Registry handler. `RegistryHandler.BLOCK_NAME.get()::yourColoredLightEvent` refers to the actual method inside your block class that handles the colored lighting. Remember to call `initRegistries()` after your mod has been set up. Please note that this code is CLIENT SIDE ONLY!

## Inside the Block constructor
To register the block from inside the constructor, your code will look something like this:
```java
package my.package.name;

import blah.blah.blah;

public class MyBlock extends Block {

   public MyBlock(Properties prop) {
        // Colored Light Blocks
        if (ModList.get().isLoaded("rgblib")) {
            ColoredLightManager.registerProvider(this, this::yourColoredLightEventName);
        }
   }
}
```

## Colored Light Method
Your Colored Light method will look something like this:
```java
public RGBLight yourColoredLightEvent(BlockPos pos, BlockState state) {
   return RGBLight.builder().position(pos).color(1.0f, 0f, 0f).radius(14).build();
}
```
`position` can either be a BlockPos or Vector3f. Color can be either a `Vector3f`, `int` or `float, float, float`.

The code above produces a Red Light with a radius of 14 (similar to the light reach of a torch). Your method can be called anything, as long as it is passed correctly to the registration code.
!!!warning
DO NOT MAKE THIS METHOD STATIC OR BLOCKS OF THE SAME KIND WILL HAVE THE SAME LIGHT AT ALL TIMES!
!!!

You can also emit colored light based on the value of a block state. For example:
```java
public RGBLight produceColoredLight(BlockPos pos, BlockState state) {
    if (state.get(LIT)) {
        return RGBLight.builder().position(pos).color(1.0f, 0f, 0f).radius(14).build();
    } else {
        return null;
    }
}
```

This will only produce light when the value of LIT is true.

And that's it! It's as simple as that. Keep in mind that this mod is designed in such a way that it is optional, which means, people can still use your mod without RGBLib installed.
