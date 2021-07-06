# How to setup TNTWars on your playerserver

First of all, make sure your server is 1.12 and you have the following plugins installed:

- Skript
- Skellett
- SkQuery
- skRayFall
- TuSKe
- Multiverse-Core
- WorldGuard

After installing the required plugins, upload all the TNTWars scripts to your server. I can ensure you that the script is not
the best but it works so I guess you'll have to live with it. After uploading the scripts, reload skript and you can start
working on your first map.

## Creating a map

### Creating the multiverse world

Creating a map is quite the hasle. First of all, make a new multiverse voidworld where you can create your map in. When your
map is created, you can start adding it to the system.

### Adding to the map manager

To add your map to the mapmanager, execute the following commands

```bash
/map admin create <mapname>
```

After which you can start editing the map itself

```bash
/map admin list
```

When seeing the list, click on the map that you want to edit. This will bring up a clickable interface in your chat where
you can setup your map. Here is a list of what each setting means:


| Type  | Meaning |
| ------------- | ------------- |
| ID | The ID of the map. This cannot be changed |
| Prefix | The name of the map |
| Author | The creator of the map |
| Item | The item that will display in the map selector |
| World | The world name of the map. Used for managing map reloading |
| RedSpawn | The location of the spawn of the red team |
| BlueSpawn | The location of the spawn of the blue team |
| Lobby | The location of the map lobby |
| Status | The status of the map, this can be enabled or construction (disabled) |


### Setting up regions

Setting up regions is probably the most annoying part of this. As it requires quite a few things to be done.

1. Select the entire side of the area of the blue team and define a region named `tntwars_<mapname>_blueteam_playarea`
2. Select the spawn of the blue team and define a region named `tntwars_<mapname>_blueteam_spawn`
3. Select the entire side of the area of the red team and define a region named `tntwars_<mapname>_redteam_playarea`
4. Select the spawn of the red team and define a region named `tntwars_<mapname>_redteam_spawn`
5. Select the lobby of the map and define a region named `tntwars_<mapname>_spawn`

> **:warning: WARNING**: Make sure you enable building & tnt in all regions so you can actually play the game!

Once you did this you successfully set up the regions for your map. And it should all be finished!

> **:warning: WARNING**: You need at least 2 maps in the mapmanager for the system to work correctly. Not doing this will probably break the system!

> **:warning: IMPORTANT**: To make dispensers filled automatically, you will need to set the variable `{tntwars::random::dispenserNBT}` to the nbt of a filled dispenser

Congratulations! You should now have a working TNTWars system on your playerserver.

## Stopping tnt from being laggy

You may notice that TNT can be a bit laggy in your playerserver. This is due to the max-tnt-per-tick being really low by default. You can fix this
by going to your file manager --> spigot.yml and changing `max-tnt-per-tick` to a really high number. After this, restart your server and everyting should work!
