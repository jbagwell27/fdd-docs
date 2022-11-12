---
order: a
title: Gradle Setup
label: Gradle Setup
---
This guide will allow you to set up the RGBLib API for usage inside your own mod.

## Forge Setup
The RGBLib api is available from my maven, so you can easily include it inside your project.

!!!info
RGBLib ONLY supports mojmap
!!!

### Adding the Maven
In your `build.gradle` file, find the section called `repositories` (this should be located above dependencies) and add the following to it (if this section doesn't exit, add it in):

For Development builds:
`maven { url = "https://maven.firstdarkdev.xyz/snapshots" }`
For Released builds:
`maven { url = "https://maven.firstdarkdev.xyz/releases" }`

Your setup would look something like this:
```gradle
repositories {
    ...existing config here
    maven { url = "https://maven.firstdarkdev.xyz/releases" }
}
```

Inside dependencies, add the following two lines:
```gradle
implementation 'net.hypherionmc:RGBLib-forge:MCVER-VERSION:api'
runtime 'net.hypherionmc:RGBLib-forge:MCVER-VERSION:api'
```

!!!info
Replace `MCVER` with your Minecraft version (for Example `1.16.5`) and `VERSION` with the latest available version (for Example `1.0`).
!!!
&nbsp;
## Fabric Setup

**COMING SOON**

---

!!!warning
The RGBLib version found on the MAVEN will not work in a normal game. To test outside of the development environment, download the build from Jenkins
!!!
When finished, save your build.gradle file and refresh your gradle. This will download and add the required files.

---

## Next Steps:

[!ref Adding a Colored Light (Block)](/rgblib/mod-dev-api/coloredblock/)
[!ref Adding a Colored Light (Item)](/rgblib/mod-dev-api/coloreditem/)
[!ref Adding a Colored Light (TileEntity)](/rgblib/mod-dev-api/coloredte/)
