---
icon: home
title: Welcome
---

To add CurseGradle to your project is really simple. At the time of writing this, the plugin is still pending approval on Gradle Plugins, so you will need to add it from my maven.

## Basic Setup
### Forge

#### Gradle Plugins Registry

To add the plugin to your project, simple add the following line to your gradle script inside the `plugins {}` section:

```gradle
id "me.hypherionmc.cursegradle" version "2.0.1"
```

#### Maven Method (Alternative Method)

To get started, you need to add my Maven and the plugin to your buildscript like this:

```gradle
buildscript {
    repositories {
        // These repositories are only for Gradle plugins, put any other repositories in the repository block further below
        maven { url = 'https://maven.minecraftforge.net' }
        maven { url = "https://maven.explodingcreeper.me/releases" }
        mavenCentral()
    }
    dependencies {
        classpath group: 'net.minecraftforge.gradle', name: 'ForgeGradle', version: '5.1.+', changing: true
        classpath 'me.hypherionmc:CurseGradle:2.0.4'
    }
}
```

Then below the `plugins` section, add
```gradle
apply plugin: 'me.hypherionmc.cursegradle'
```

Then, at the bottom of the file, add this:

```gradle
curseforge {
    apiKey = "" // This should be kept private.
    options {
        forgeGradleIntegration = true
    }
    project {
        id = '12345' // The ID of your project. You can find this on your project Curseforge page
        changelog = 'Changes' // A file can also be set using: changelog = file('changelog.txt')
        releaseType = 'beta' // beta, alpha, release
        mainArtifact(reobfJar) {
          displayName = "MyMod version: $project.version"
        }
    }
}
```

&nbsp;

## Fabric

#### Gradle Plugins Registry

To add the plugin to your project, simple add the following line to your gradle script inside the `plugins {}` section:

```gradle
id "me.hypherionmc.cursegradle" version "2.0.1"
```

Open your `settings.gradle` file and add this to the `repositories` section:

```gradle
maven {
    url = 'https://maven.explodingcreeper.me/'
}
```

#### Maven Method (Alternative Method)

So the file should look something like this:

```gradle
pluginManagement {
    repositories {
        jcenter()
        maven {
            name = 'Fabric'
            url = 'https://maven.fabricmc.net/'
        }
        maven {
            url = 'https://maven.explodingcreeper.me/'
        }
        gradlePluginPortal()
    }
}
```

Then head over to your `build.gradle` file and add this above `plugins`:

```gradle
buildscript {
    dependencies {
        classpath 'me.hypherionmc:CurseGradle:2.0.4'
    }
}
```

Then below `plugins` add

```gradle
apply plugin: 'me.hypherionmc.cursegradle'
```

Then, at the bottom of the file, add this:

```gradle
curseforge {
    apiKey = "" // This should be kept private.
    options {
        forgeGradleIntegration = false
        fabricIntegration = true // This automatically adds Fabric and your Minecraft Version as a game version
        detectFabricApi = true // This will automatically add the Fabric API as a required dependency
    }
    project {
        id = '12345' // The ID of your project. You can find this on your project Curseforge page
        changelog = 'Changes' // A file can also be set using: changelog = file('changelog.txt')
        releaseType = 'beta' // beta, alpha, release
        mainArtifact(remapJar) {
          displayName = "MyMod version: $project.version"
        }
    }
}
```
