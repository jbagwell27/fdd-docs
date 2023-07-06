---
title: Modrinth/Curseforge Dependencies
order: b
---

Sometimes, a mod requires some additional dependencies to work. This can be easily added with the following blocks:

||| Curseforge

```groovy
curseDepends {
    required = ["fabric-api", "cloth-config"] // Required Dependencies
    optional = ["cofh-core"] // Optional Dependencies
    incompatible = ["fancy-menu"] // Incompatible dependencies
    embedded = ["my-api"] // Embedded dependencies
}
```
|||

||| Modrinth

```groovy
modrinthDepends {
    required = ["P7dR8mSH"] // Required Dependencies
    optional = ["nOiHJ1dx"] // Optional Dependencies
    incompatible = ["AANobbMI"] // Incompatible dependencies
    embedded = ["hvFnDODi", "9s6osm5g"] // Embedded dependencies
}
```
|||

||| Full Example

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
    version = "1.3.0" // Used by Modrinth and GitHub
    displayName = "MyAwesome Mod - Version" // Friendly display name for the file
    gameVersions = ["1.19.3", "1.19.4"] // Supported Game Versions
    loaders = ["forge", "fabric", "quilt"] // Supported Modloaders
    artifact = jar // File or file location of the file to upload

    modrinthDepends {
        required = ["P7dR8mSH"] // Required Dependencies
        optional = ["nOiHJ1dx"] // Optional Dependencies
        incompatible = ["AANobbMI"] // Incompatible dependencies
        embedded = ["hvFnDODi", "9s6osm5g"] // Embedded dependencies
    }

    curseDepends {
        required = ["fabric-api", "cloth-config"] // Required Dependencies
        optional = ["cofh-core"] // Optional Dependencies
        incompatible = ["fancy-menu"] // Incompatible dependencies
        embedded = ["my-api"] // Embedded dependencies
    }
}
```
|||