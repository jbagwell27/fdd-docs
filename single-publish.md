---
title: Publish to a Single Platform
order: c
---

If you do not wish to publish to every supported platform, disabling them is easy.

For example, if you don't want to publish to GitHub, just remove `github` from the `apiKeys` section

```diff
publisher {
    apiKeys {
        curseforge = System.getenv("CURSE_TOKEN") // Required if you want to use Curseforge Upload
        modrinth = System.getenv("MODRINTH_TOKEN") // Required if you want to use Modrinth Upload
-       github = System.getenv("GITHUB_TOKEN") // Required if you want to use GitHub releases
    }
    
    ...    
}
```

So it becomes:


```groovy
publisher {
    apiKeys {
        curseforge = System.getenv("CURSE_TOKEN") // Required if you want to use Curseforge Upload
        modrinth = System.getenv("MODRINTH_TOKEN") // Required if you want to use Modrinth Upload
    }
    
    ...    
}
```
