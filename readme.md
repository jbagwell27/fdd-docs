---
icon: home
title: Getting Started
---
ModPublisher is a Gradle Plugin that allows modders to publish their mods to Modrinth, Curseforge and GitHub in one go.

No need for separate plugins, just one!

This plugin is mostly aimed at projects using MultiLoader Template and for our internal use, but anyone is free to use it.

---

||| Installing the Plugin

To use this plugin inside your project, first you have to add our maven.

To does this, open up `settings.gradle` and add the following:

```groovy
pluginManagement {
    repositories {
        gradlePluginPortal()
        maven {
            url "https://maven.firstdarkdev.xyz/releases"
        }
    }
}
```

Next, in your `build.gradle` add:

![](https://maven.firstdarkdev.xyz/api/badge/latest/releases/me/hypherionmc/modutils/modpublisher?color=40c14a&name=modpublisher)

```groovy
plugins {
    id "me.hypherionmc.modutils.modpublisher" version "VERSION"
}
```

Replace VERSION with the version above.
|||

||| Basic Setup

Add this into your `build.gradle` file:

```groovy
publisher {
    apiKeys {
        curseforge = System.getenv("CURSE_TOKEN") // Required if you want to use Curseforge Upload
        modrinth = System.getenv("MODRINTH_TOKEN") // Required if you want to use Modrinth Upload
        github = System.getenv("GITHUB_TOKEN") // Required if you want to use GitHub releases
    }

    debug = false // When enabled, no files will actually be uploaded
    curseID = 12345 // Curseforge Project ID
    modrinthID = xyn8677dh // Modrinth Project ID
    githubRepo = "OWNER/REPO" // For example, https://github.com/firstdarkdev/modpublisher OR firstdarkdev/modpublisher
    versionType = "release" // Release Type. Either release, beta, or alpha
    changelog = "changelog.md" // Changelog file, or text. Only MARKDOWN is supported
    version = "1.3.0" // Used by modrinth and GitHub
    displayName = "MyAwesome Mod - Version" // Friendly display name for the file
    gameVersions = ["1.19.3", "1.19.4"] // Supported Game Versions
    loaders = ["forge", "fabric", "quilt"] // Supported Modloaders
    curseEnvironment = "both" // Set the new Curseforge mod type. Valid entries are client, server or both
    disableMalwareScanner = true // Disable the built in fractureiser scanner
    disableEmptyJarCheck = true // Disable checking if the required meta file for the modloaders are present in the jar. For example, fabric.mod.json on fabric and quilt
    artifact = jar // File or file location of the file to upload
    useModrinthStaging = false // Upload to modrinth Staging
    additionalFiles = [javadocJar, sourcesJar] // Additional files to upload
}
```
|||

[!ref Modrinth/Curseforge Dependencies](dependencies/)
