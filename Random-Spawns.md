Random Mob Spawners
===================

Random mob spawners give you complete control over how mobs are supposed
to spawn in your worlds. You can fully customize where, how often and
how many mobs spawn and make your spawning system precise by utilizing a
variety of condition-options.

Important Differences
---------------------

There are major randomspawn options that are important to distinguish
between:

-   **Action: REPLACE**
    -   The replace-action is used to replace mobs that are spawned by
        minecraft's very own random spawning system with your custom
        mythic mob creations. 
    -   This allows for full control over minecraft's spawning system. 
    -   If Minecraft's random spawners are turned off on your server, examply by setting gamerule doMobSpawning false, this action will not do anything.
        
        

<!-- -->

-   **Action: ADD**
    -   The add-action will utilize MythicMobs' very own spawning algorithms which will, in a similar fashion to Minecraft's spawning system, generate random spawn points around players.
    -   However these spawn points, as opposed to Minecraft's, will be generated without any conditions allowing you to spawn mobs in any light level and at any location.
    -   Detailed configurations as to how these spawn points are generated can be found in MythicMobs' configuration file "config.yml".
    -   **Please note** Action: ADD only generates points around survival & adventure mode players and if there is only a location present.
    -   If a condition is used that needs an entity it will throw an exception. In case of the biome condition you can use the Biomes: option!
    -   For the Action: ADD to work, you will need to go to your plugins/MythicMobs/config.yml and set GenerateSpawnPoints to true!

<!-- -->

-   **Action: DENY**
    -   The Deny action can be used to prevent mobs from spawning.
    -   Any mob that matches the conditions of a RandomSpawn configured with DENY will not spawn.

<!-- -->

-   **Action: SCALE**
    -   *upcoming feature*

Options
-------

A complete list of all available randomspawn options.

### Global Randomspawn Options

**Example:**

    my_favorite_randomspawn:
      Action: ADD
      Type: cute_zombie
      Level: 2
      Chance: 0.01
      Priority: 10
      UseWorldScaling: false
      Worlds: my_overworld,my_overworld_nether

-   **Action: \[action\]**
    -   The spawning method to utilize, defaults to "ADD"
    -   Action: ADD
    -   Action: REPLACE

<!-- -->

-   **Type: \[mobtypes\]**
    -   Defines the type of mob(s) to be spawned. Can be an array/multiple mob types
    -   Type: SuperZombie
    -   Type: SkeletalMage,WitchBoss
    -   May also be MobType or MobName

<!-- -->

-   **Level: \[number\]**
    -   The level the specified mob(s) should spawn with.
    -   Must be a fixed number, will not parse number ranges
    -   May be overriden by world scaling settings (see below for
        options)
    -   Defaults to 1
    -   Level: 7

<!-- -->

-   **Chance: \[number\]**
    -   The chance for the mob(s) to spawn.
    -   Defaults to 1 [1]
    -   **Chance: 0.025**

<!-- -->

-   **Priority: \[number\]**
    -   The priority used to determine which randomspawn to prefer, when
        multiple mobs are chosen to be spawned at the same spawn point
    -   Rule of thumb: *higher priority number = higher chance to be
        selected when multiple mobs are chosen*
    -   Defaults to 1
    -   **Priority: 128**

<!-- -->

-   **UseWorldScaling: \[true/false\]**
    -   Wether the spawned mob's level should be affected by the world
        scaling settings
    -   Defaults to true

<!-- -->

-   **Conditions: \[list\]**
    -   A list of conditions used to further shape the spawning
        conditions of the specified mobs
    -   The random spawn will fail if any of the given conditions aren't
        met
    -   The full list of available conditions can be found here:
        [Conditions manual page](/Skills/Conditions#conditions)
    -   **Conditions:**
    -   **- condition 1**
    -   **- condition 2**
    -   **...**

<!-- -->

-   **Worlds: \[worldnames\]**
    -   The names of worlds in which the randomspawns should be applied.
    -   Can be an array / multiple worlds
    -   These names correspond to how your minecraft worlds are named in
        the gamefiles
    -   **Worlds: world**
    -   **Worlds: world,world\_the\_end,world\_nether**
    -   **Worlds: jays\_overworld**

<!-- -->

-   **Biomes: \[biomes\]**
    -   The biomes the specified mobtype(s) can spawn inside of.
    -   Can be an array / multiple biomes
    -   **Biomes: SNOWY\_TUNDRA,ICE\_SPIKES,SNOWY\_TAIGA,...**

<!-- -->

-   **Reason: \[reason\]**
    -   The reason of minecraft-randomspawn to be matched
    -   Can be an array / multiple reasons
    -   If this option exists, the randomspawn will only work if it
        matches one of the specified reasons
    -   Can be anything from this list:
        [CreatureSpawnEvent.SpawnReason](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/entity/CreatureSpawnEvent.SpawnReason.html)
    -   **Reason: NATURAL**

<!-- -->

-   **PositionType: \[LAND/SEA\]**
    -   Whether this RandomSpawn should use land or sea points to spawn
    -   Only does anything with Action: ADD
    -   **PositionType: LAND**

### Extra Options in config.yml

These options, located in MythicMobs' "config.yml"-file, are responsible
for how Mythic-SpawnPoints are generated on your server. If you're
upgrading to MythicMobs 2.3 from a previous version, you must regenerate
your config.yml in order to have these options added to it. Use common
sense when adjusting these values, as misconfigurations of this section
may cause lag on your server.

      RandomSpawning:
        GenerateSpawnPoints: true
        MaxMobsPerChunk: 3
        SpawnRadiusPerPlayer: 64
        SpawnRadiusPerPlayerY: 32
        DespawnLazyRandomMobs: true
        PointsPerSecond:
          Land: 10
          Sea: 5

Examples
--------

In-depth tutorial on how to create random spawners: [Creating Random
Spawners](/tutorials/randomspawns)

[1] 1 = 100 %, 0.5 = 50 % ...