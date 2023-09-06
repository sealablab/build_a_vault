---
title: Introducing your .obsidian directory 
---
# Introducing your `.obsidian` directory
Welcome to your very own  `dot obsidian` directory!
This is where obsidian will store configuration information about your `Vault`
Here is what you will get by default

```
user:~/build_a_vault/2$ wc -l ./.obsidian/* 
       0 ./.obsidian/app.json
       2 ./.obsidian/appearance.json
       0 ./.obsidian/hotkeys.json
      21 ./.obsidian/core-plugins.json
      29 ./.obsidian/core-plugins-migration.json
```

## .obsidian/app.json 
Although this file is empty, I'm pretty sure Obsidian uses it as some sort of flag to indicate that directory containing it has been previously initiailzed as a vault.

## .obsidian/appearance.json
Pretty self descriptive. By default it just contains the following
``` json
{
  "accentColor": ""
}
```
## .obsidian/hotkeys.json
Initialized to zero bytes. This is where our own hotkey settings will be stored eventually. 

## .obsidian/core-plugins.json
This appears to be a list of all the `core-plugins` that obsidian enables by default.
```
.obsidian johnycsh$ wc -l core-plugins.json
21 core-plugins.json
.obsidian johnycsh$ cat ./core-plugins.json | head -n 8 | jq
```

``` json
[
  "file-explorer",
  "global-search",
  "switcher",
  "graph",
  "backlink",
  "canvas",
  "outgoing-link",

```



## .obsidian/core-plugins-migration.json
By default this contains 29 entries.
I'm not entirely sure what this file actually does, but here is a representative sample before moving on
```
{
  "file-explorer": true,
  "global-search": true,
  "switcher": true,
  "graph": true,
  "backlink": true,
  "canvas": true,
  "zk-prefixer": false,
  "workspaces": false,
  "file-recovery": true,
  "publish": false,
  "sync": true
}
```



