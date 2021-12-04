# Optimized Paper Config 

Optimized versions of the default PaperMC configuration files for low end
severs or to just improve performance in general.

⚠️ Some plugins may break and some minor gameplay features will cease to function
with this config enabled.

ℹ️ Based on [this amazing guide](https://www.spigotmc.org/threads/guide-server-optimization%E2%9A%A1.283181/?__cf_chl_f_tk=jxvHzt6IuNzSnHr4Y8gcpw38tyVT7OIOwAS4ZE0Ok.Q-1638642015-0-gaNycGzNCWU)
by Calebrimbor, please check out their guides on server optimization and lag if you have the time, because they are amazing.

## Installation

Simply go into the root directory of your server files and replace "bukkit.yml",
"paper.yml", "server.properties", and "spigot.yml" with the files included in 
the Config folder of this github repository.

## Reporting Issues

Report issues by opening an issue on the issue tracker, if the config is causing
your issue make sure your report includes. 

1. A screenshot of the issue
2. An explanation of what is happening in the screenshot
3. What's supposed to be happening in the screenshot if the issue wasn't present
4. What you think may be causing the issue inside of the config

If your issue has to do with Paper itself or something else, then I cannot help you.

## Configuration

Some of the items changed in this config can cause minor issues for the sake
of performance which you may want to avoid.

- **Default:** Values set by default.
- **Optimized:** Values changed in this config for optimization purposes.

### Bukkit.yml
Changes made to the Bukkit.yml file and what they do.

#### spawn-limits
Sets the spawn limits of various different mobs, you may want to change this
if you have concerns about the values set.

- **Default:** monsters:70, animals:10, water-animals:15, water-ambient:20, ambient:15
- **Optimized:** monsters:50, animals:8, water-animals:7, water-ambient:10, ambient:1

#### chunk-gc.period-in-ticks
How fast to unload vacant chunks, lower values unload them faster, higher values
unload them slower

- **Default:** 600
- **Optimized:** 400

#### ticks-per.(type)-spawns
How often (in ticks) the server attempts to spawn entities higher values will
increas the time between spawn attempts

- **Default:** monster:1, water:1, water-ambient:1, ambient:1
- **Optimized:** monster:5, water:11, water-ambient:21, ambient:31

### Spigot.yml
Changes made to the Spigot.yml file and what they do.

#### save-user-cache-on-stop-only
If this is set to true it will only save/cache user data when the server stops
or restarts, if it is set to false it will constantly save user data.

- **Default:** false
- **Optimized:** true

#### mob-spawn-range
Sets the max mob spawning distance (in chunks) from players, higher values 
means that mobs can spawn further away, lower values reduce the distance mobs
can spawn from players.

- **Default:** 8
- **Optimized:** 6

#### entitiy-activation-range
Entities past this range will be ticked less often

- **Default:** animals:32, monsters:32, raiders: 48, misc:16
- **Optimized:** animals:16, monsters:24, raiders: 48, misc:8

#### tick-inactive-villagers
If set to true will tick villagers outside of the activation range, if set to 
false will not.

- **Default:** True
- **Optimized:** False

#### merge-radius
The distance items on the ground will merge, higher values means items on the 
ground will merge at a greater distance, lower values means items on the ground
will merge at a smaller distance.

- **Default:** item:2.5, exp:3.0
- **Optimized:** item:4.0, exp:6.0

#### item-despawn-rate
The time in ticks before an item on the ground is removed, It's recomended to
change this to a higher value or to the default value if you dont like
items despawning quicker.

- **Default:** 6000
- **Optimized:** 3000

#### arrow-despawn-rate
The time in ticks before a shot arrow despawns, you may want to change this if
you want arrows to despawn quicker or slower.

- **Default:** 1200
- **Optimized:** 300

### Paper.yml
Changes made to the Paper.yml file and what they do.

#### max-auto-save-chunks-per-tick
The maximum amount of chunks that will autosave per tick.

- **Default:** 24
- **Optimized:** 6

#### optimize-explosions
A more efficient algorithm for optimizing explosions built into paper

- **Default:** false
- **Optimized:** true

#### mob-spawner-tick-rate
The delay (in ticks) before an active mob spawner attempts to spawn mobs

- **Default:** 1
- **Optimized:** 2

#### disable-chest-cat-detection
The server will check if there is a cat on top of a chest opened by a player,
if so it will prevent the chest from being opened, if this value is set to false
it will disable this mechanic entirely

- **Default:** false
- **Optimized:** True

#### container-update-tick-rate
How often in ticks inventories are refreshed while open

- **Default:** 1
- **Optimized:** 3

#### max-entitiy-collisions
The maximum ammount of entity collisions higher values will allow for more
entitiy collisions while lower values will allow for less entity collisions

- **Default:** 8
- **Optimized:** 2

#### grass-spread-tick-rate
The time in ticks before grass begins to spread in loaded chunks

- **Default:** 1
- **Optimized:** 4

#### despawn-ranges
The ranges for despawning mobs, Soft is the distance in blocks from a player 
where mobs will be periodically removed, Hard is the distance in blocks from
a player where mobs are removed instantly

- **Default:** soft: 32, hard: 128
- **Optimized:** soft: 28, hard: 96

#### hopper.disable-move-event
If set to true will prevent InventoryMoveItemEvent being called for every slot 
in a container. You may want to disable this if you have a plugin that relies
on InventoryMoveItemEvent.

- **Default:** false
- **Optimized:** true

#### non-player-arrow-despawn-rate
The amount of time (in ticks) it takes for an arrow not fired by a player to 
despawn.

- Default: -1 (Uses Spigot's arrow-despawn-rate)
- Optimized: 60

#### creative-arrow-despawn-rate
Similar to non-player-arrow-despawn rate but with arrows fired while in creative
or arrows fired with an infinity bow

- Default: -1 (Uses Spigot's arrow-despawn-rate)
- Optimized: 60

#### prevent-moving-into-unloaded-chunks
If set to true will prevent players from entering an unloaded chunk which can 
cause lag.

- Default: false
- Optimized: true

#### use-faster-eigencraft-redstone
If set to true will use papers optimized redstone algorithm which has been shown
to reduce unnessisary redstone updates and greatly improve redstone's speed
and performance.

- Default: false
- Optimized: true

#### armor-stands-tick
Unlike traditional blocks, armor stands are considered entities because they
are able to interact with the world. Disabling this will just make it so
they are unable to interact with pistons, water, or other things.

- Default: true
- Optimized: false

#### per-player-mob-spawns
If set to true will implement spawning behavior similar to a singleplayer world, 
this prevents stuff like massive mob farms from affecting the server's spawn
rates.

- Default: false
- Optimized: true

#### alt-item-despawn-rate
Despawn certain item drops faster or slower than the despawn rate set in Spigot
if set to true. Use the Spigot material list when adding items.

- Default: false
- Optimized: true

### Server.properties
Changes made to the Server.properties file and what they do.

#### view-distance
Allows you to cap the chunk render distance of players

- Default: 10 
- Optimized: 10 (Value not changed)

#### network-compression-threshold
The maximum size of a packet before the server compesses it, Higher values will
take less resources but more bandwith, lower values will take more resources 
but less bandwith.

- Default: 256
- Optimized: 128




