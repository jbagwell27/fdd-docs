---
order: a
title: Advanced configuration
---

## All the possibilities

### Artifacts
Any argument below that takes an artifact, that would be `mainArtifact` and `addArtifact` currently, can be customized individually. Each artifact can have the following properties defined:

* `changelogType`: The type of changelog. This can be: `text`, `html`, or `markdown`. The default is `text`.
* `changelog`: A list of changes for the current build. This can be a `String` or a `File`. If a file is set, its contents will be used. **This is a required field**.
* `displayName`: A user-friendly display name for the artifact. This can be a `String` or a `File`. If a file is specified, its contents will be used.
* `releaseType`: One of `alpha`, `beta`, or `release`. This tells end users how stable the file is. Once again, a file can be specified if you so desire. **This is a required field**.
* `relations`: Dependencies, incompatibilities, or relationships with other projects on CurseForge. *This can also be specified on the project level*. To get the project's unique slug, look in the URL on CurseForge Example: Railcraft: `https://www.curseforge.com/minecraft/mc-mods/railcraft`, the slug is `railcraft`.
```gradle
curseforge {
  project {
    mainArtifact(jar) {
      relations {
        requiredDependency 'railcraft' // Railcraft is required
        embeddedLibrary 'cofhlib' // CoFH Lib is shipped with the artifact
        optionalDependency 'notenoughitems' // Not Enough Items is an optional addon
        tool 'worldedit' // World Edit is a compatible tool
        incompatible 'buildcraft' // BuildCraft is not compatible
      }
    }
  }
}
```

**All of the above properties, with the exception of `displayName` can also be set in the `project { }` block and it will apply to all artifacts of the project that don't override it.**
```gradle
curseforge {
  project {
    releaseType = 'beta'
    changelogType = 'html'
    changelog = '<h2>Big Changes!</h2>'
    relations {
      requiredDependency 'railcraft'
    }
  }
}
```
&nbsp;
### Project Settings

#### `apiKey` - ***Required***
This can be applied globally:
```gradle
curseforge {
  apiKey = '...'
}
```
or per project if you have multiple projects with different API keys:
```groovy
curseforge {
  project {
    apiKey = '123456'
  }
  project {
    apiKey = '456789'
  }
}
```

#### `id` - ***Required***

The project ID on CurseForge. This is the numerical part of the URL.
```gradle
curseforge {
  project {
    id = '12345'  
  }
}
```

#### `mainArtifact` - ***Required***

The main artifact is applied per project and should be the primary binary produced by the build. ***Although this is a required field, it can be left out if the `java` gradle plugin is applied. If so, the java `jar` task will be selected automatically.***
```gradle
curseforge {
  project {
    mainArtifact jar
  }
}
```

#### `addGameVersion` - ***Required***

Add a version of Minecraft that is compatible with this upload. ***If [ForgeGradle](https://github.com/MinecraftForge/ForgeGradle) is applied, this field can be left out and will be pulled from ForgeGradle.***
```gradle
curseforge {
  project {
    addGameVersion '1.12.2'
  }
}
```

#### `addArtifact`

Additional artifacts can be uploaded in addition to the primary `mainArtifact`
```gradle
curseforge {
  project {
    addArtifact sourcesJar
  }
}
```

&nbsp;

### Options

Additional options to control integration with other features can be controlled in the options section.
```gradle
curseforge {
  project {
    //...
  }
  options {
    debug = false // defaults to false
    javaVersionAutoDetect = true // defaults to true
    detectNewerJava = false // defaults to false
    javaIntegration = true // defaults to true
    forgeGradleIntegration = true // defaults to true
  }
}
```

#### `debug`
Debug mode will stop just short of actually uploading the file to Curse, and instead spit out the JSON to the console. Useful for testing your buildscript.
```gradle
curseforge {
  project {
    //...
  }
  options {
    debug = true // defaults to false
  }
}
```

#### `javaVersionAutoDetect`
If this is left enabled, CurseGradle will automatically detect the compatible versions of Java for the project and add them to the CurseForge metadata.
```gradle
curseforge {
  project {
    //...
  }
  options {
    javaVersionAutoDetect = false // defaults to true
  }
}
```

#### `detectNewerJava`
If this is enabled, CurseGradle will detect Java 9 and later versions of Java for the project and add them to the CurseForge metadata.
```gradle
curseforge {
  project {
    //...
  }
  options {
    detectNewerJava = true // defaults to false
  }
}
```

#### `javaIntegration`
Enable integration with the Gradle Java plugin. This includes setting the default artifact to the jar task.
```gradle
curseforge {
  project {
    //...
  }
  options {
    javaIntegration = false // defaults to true
  }
}
```

#### `forgeGradleIntegration`
Enable integration with the ForgeGradle plugin. This includes setting dependencies on the reobfuscation tasks.
Set this to false to disable automatic rebuild, e.g. if you want to push the same artifact to multiple destinations (GitHub releases, ...).
```gradle
curseforge {
  project {
    //...
  }
  options {
    forgeGradleIntegration = false // defaults to true
  }
}
```

#### `fabricIntegration`
Enable integration for fabric mods. This will attempt to detect the Minecraft version from the mod and add it as a game version. This will also add the Fabric API as a required dependency on the main artifact, if `detectFabricApi` is enabled (true by default)
```gradle
curseforge {
  project {
    //...
  }
  options {
    forgeGradleIntegration = false // defaults to true
    fabricIntegration = true // defaults to true
    detectFabricApi = true // defaults to true
  }
}
```

