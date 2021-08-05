Spawners
========

Spawners allow you to define specific points in your worlds at which your custom mob creations can spawn. They can with a variety of useful options, conditions and built-in timers, cooldowns and warmups. Note that in MythicSpawners you can only use the old conditions system. Here can you find them: [Legacy Conditions](/conditions/legacyconditions)

You can create spawners directly ingame by using [Commands](/commands and permissions) and by creating the a configuration file in the folder */MythicMobs/Spawners*. Note that once a spawner-configuration file has been loaded onto a running server, it can only be edited by ingame commands. If you want to edit a already loaded spawner-configuration file in a text-editor, you have to stop the server in the meantime.

### Pros of Spawners

-   Doesn't require natural mob spawning to be enabled to work.
-   Allows for a much more specific and consistent implementation because you can specify exactly where and how each mob spawn.
-   Support timers, leashing and other features.
-   Good to populate small arenas or dungeons.

### Cons of Spawners

-   Setup can be time consuming especially for larger implementations.
-   Can become very difficult to manage if not planned out correctly.
-   Mobs need to be configured appropriately.
-   Despawn false isnt a option that is meant to be used in mythic spawners.

Example Config
--------------
```
SpawnerName:
  MobName: mobTypeName 
  World: worldname
  SpawnerGroup: GroupName
  X: 0 
  Y: 0 
  Z: 0 
  Radius: 0 
  RadiusY: 0 
  UseTimer: true  
  MaxMobs: 1
  MobLevel: 1
  MobsPerSpawn: 1
  Cooldown: 0
  CooldownTimer: 0
  Warmup: 0
  WarmupTimer: 0
  CheckForPlayers: true
  ActivationRange: 40
  LeashRange: 32
  HealOnLeash: false
  ResetThreatOnLeash: false
  ShowFlames: false
  Breakable: false
  Conditions: []
  ActiveMobs: 1
```
Options
-------
| Option             | Description                      |Usage                       |Default|
|--------------------------|-----------------------|-----------------------|-----------------------|
|**mobtype: &lt;mobtype&gt;** or **mobname: &lt;mobtype&gt;:**|This is mob type that the spawner will spawn. Can only be set to an internal MythicMobs mob. Allows for an array of mobs with weightings.|/mm s set [name] mobtype 25%Mob1,25%Mob2,50%mMob2| N/A |
|**world: &lt;worldname&gt;:**|    This is the filename of the world where the spawner is located|    /mm s set <name> world <world>|Creation World|
|**spawnergroup: &lt;group name&gt;**|This sets the group name for the spawn. For larger configurations, such as if you are populating a dungeon, you can group all spawners and then change the settings for them all at the same time.|/mm s set g:<group> <setting> <value>|N/A|
|**X: / Y: / Z:**|Coordinates of the spawner||Creation Location|
|**radius: &lt;number&gt;**|This is the radius around the spawner at which the mob can spawn.| /mm s set <name> radius <radius>|0|
|**radiusY: &lt;number&gt;**|This is the vertical radius around the spawner at which the mob can spawn|/mm s set <name> radiusy <radius>|0|
|**usetimer: &lt;true/false&gt;**|Whether or not the spawner activates on a timer.|/mm s set <name> usetimer <true/false>|True|
|**maxmobs: &lt;number&gt;**|This is the max number of mobs that can be spawned and existing in the world for this spawner. **Must be equal to or greater than mobsperspawn**|/mm s set <name> maxmobs <amount>|1|
|**moblevel: &lt;number&gt;**|This is the level of the mob that should spawn from this spawner. Mob must have level configuration for this to work.|/mm s set <name> moblevel <level>|1|
|**mobsperspawn: &lt;number&gt;**|This is the number of mobs spawned each time the spawner spawns a mob.|/mm s set <name> mobsperspawn <amount>|1|
|**cooldown: &lt;number&gt;**|This the amount of time in seconds that the spawner waits after a mob has been spawned before another mob is spawned.|/mm s set <name> cooldown <time>|0|
|**cooldowntimer: &lt;number&gt;**|This option is set automatically by the spawner. Used to bridge cooldowns over server reboots.|*does not require any user setting*||
|**warmup: &lt;number&gt;**|The amount of time in seconds before the spawner starts cooldown. Warmup starts on activation and if maxmobs is reached and a mob dies.|/mm s set <name> warmup <duration>|0|
|**warmuptimer: &lt;number&gt;**|This option is set automatically by the spawner, used to bridge warmups over server reboots.|*does not require any user setting*.||
|**checkforplayers: &lt;true/false&gt;**|Whether or not players must be near the spawner for it to "activate"||true (recommended for performance)|
|**activationrange: &lt;number&gt;**|What radius must players be within for the spawner to activate.||40 blocks|
|**leashrange: &lt;number&gt;**|This is the max distance that a mob can move from its spawn location before it is teleported back.|/mm s set <name> leashrange <distance>|-1(none)|
|**healonleash: &lt;true/false&gt;**|Whether the mob should heal to full health when it leashes back to its spawner|/mm s set <name> healonleash <true/false>|false|
|**resetthreatonleash: &lt;true/false&gt;**|Resets ThreatTables (if enabled) when a mob teleports back to its spawner.||false|
|**showflames: &lt;true/false&gt;**|Set this to true to show flames around the spawner.|/mm s set <name> showflames <true/false>|false|
|**breakable: &lt;true/false&gt;**|Determines if the spawner is broken with the block it is placed on||false|
|**conditions:**|Set conditions to be met for the spawner to activate.| MythicSpawners can only use the legacy conditions system.|[Find them here](/conditions/legacyconditions)||
|**activemobs: &lt;number&gt;**|Used to keep track of mobs connected to (spawned by) the spawner.|*it does not require any user setting*.||

**Note on timing of spawns:** ```Timing: warmup-> mob spawns-> cooldown-> mob spawns*>```