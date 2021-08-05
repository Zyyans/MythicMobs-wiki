Pre-2.0 Changelogs
------------------

### v1.1.8

#### General

Updated MythicMobs with 1.8 support.

#### Commands

Added **/mm spawners cut \[search\_string\]**, **/mm spawners paste**
and **/mm spawners undo** commands.

These commands can be used to move large amounts of spawners at once
while retaining their relative position. It can even be used to move
them to other worlds. (Cuts and pastes in the same way that WorldGuard
would)

\[search\_string\] can accept a number of expected inputs. Here are some
examples:

-   **/mm spawners cut g:BoneCastle** - cuts all spawners in the
    BoneCastle group
-   **/mm spawners cut r:200** - cuts all spawners in a 200 block radius
-   **/mm spawners cut Elementals\_**\* - cuts all spawners with names
    starting with *Elementals\_*
-   \*\*/mm spawners cut \*\*\* - cuts ALL spawners in the world

**/mm spawners paste** moves the spawners. You can do it multiple times
but the paste will overwrite any previous pastes with the same cut since
spawners still require their unique names preserved.

**/mm spawners undo** will undo the last spawners you cut and put them
back where they originally were when you did the cut as long as you
still have the same spawners selected.

#### Mobs

Added new 1.8 mobs for 1.8 servers! Please use the latest 1.8 Spigot
build or these will not work.

##### ARMOR\_STAND

Creates a Mythic Armor\_Stand. Do with it what you will.

ARMOR\_STAND options:

-    Options.HasArms: (true/false)
-    Options.HasGravity: (true/false)
-    Options.Small: (true/false)
-    Options.Invisible: (true/false)
-    Options.ItemHead: \[MythicItem Name\]
-    Options.ItemBody: \[MythicItem Name\]
-    Options.ItemLegs: \[MythicItem Name\]
-    Options.ItemFeet: \[MythicItem Name\]
-    Options.ItemHand: \[MythicItem Name\]

##### GUARDIAN

##### ELDER\_GUARDIAN

##### ENDERMITE

##### RABBIT

#### Bug Fixes/Other

-   Particle effects can now be seen from much further away on 1.8
-   Fixed some errors with AI on certain Bukkit versions
-   Fixed a bunch of assorted NPE errors
-   Fixed various other minor bugs

### v1.1.4

**NOTICE: v1.1.x contains major re-written mob spawning code. Most mob
configs will still work normally except most mobs containing the words
"angry" or "baby" will no longer work. "Angry" and "Baby" have been
separated into options (Angry, Age and AgeLock respectively) because
they were not really mob types. Real mob variants such as BABY\_ZOMBIE
will still work.**

#### AI Controls

-   AI Controls are now backwards compatible with all supported Bukkit
    versions.
-   Custom AI should now work on the Spigot 1.8 compatibility builds.

#### Skills

-   Added **title** skill, only works on 1.8 Spigot compatibility build.

<!-- -->

    Skills:
    - title [radius]:[fadeInTicks]:[displayTicks]:[fadeOutTicks]:"Title":"Subtitle"

#### API

-   Added some new API methods for the Spawn event

#### Bug Fixes/Other

-   Fixed a bunch of assorted NPE errors
-   Fixed ThreatTable error when target goes to a different world
-   Fixed various other minor bugs

### v1.1.2

**&lt;&lt;color red&gt;&gt;NOTICE: v1.1.x contains major re-written mob
spawning code. Most mob configs will still work normally except most
mobs containing the words "angry" or "baby" will no longer work. "Angry"
and "Baby" have been separated into options (Angry, Age and AgeLock
respectively) because they were not really mob types. Real mob variants
such as BABY\_ZOMBIE will still work.&lt;&lt;/color&gt;&gt;**

#### Bug Fixes/Other

-   Fixed a critical bug where mob timer abilities would sometimes
    continue firing after death or despawning
-   Fixed a console error involving mobs that did not have equipment
-   Fixed a console bug thrown by mobs without certain options defined
-   Fixed an NPE error on mob spawn for mobs without Skills
-   Fixed an NPE error on mob damage for mobs without DamageModifiers

### v1.1.1

**&lt;&lt;color red&gt;&gt;NOTICE: v1.1.x contains major re-written mob
spawning code. Most mob configs will still work normally except most
mobs containing the words "angry" or "baby" will no longer work. "Angry"
and "Baby" have been separated into options (Angry, Age and AgeLock
respectively) because they were not really mob types. Real mob variants
such as BABY\_ZOMBIE will still work.&lt;&lt;/color&gt;&gt;**

#### Spawners

-   Added RadiusY option to spawners

#### Bug Fixes/Other

-   Improved error-checking for mobs and spawners to prevent certain
    startup errors.
-   Fixed Creeper-specific options not being applied.
-   Fixed effects targeting spawners to target the center of blocks
-   Fixed a bug with preventSuicide creeper option not working in most
    cases
-   Fixed an alias for MagmaCube not working properly
-   Fixed a bug preventing Slime and MagmaCube options from applying
-   Fixed a bug preventing options that apply to after-death events from
    functioning
-   Fixed (hopefully) mob custom AI not persisting through chunk reloads

### v1.1.0

**&lt;&lt;color red&gt;&gt;NOTICE: v1.1.x contains major re-written mob
spawning code. Most mob configs will still work normally except most
mobs containing the words "angry" or "baby" will no longer work. "Angry"
and "Baby" have been separated into options (Angry, Age and AgeLock
respectively) because they were not really mob types. Real mob variants
such as BABY\_ZOMBIE will still work.&lt;&lt;/color&gt;&gt;**

#### New Features

##### AI Controls

-   Ability to clear, add to and modify a mob's AI Pathfinder Goals
-   Ability to clear, add to and modify a mob's AI TargetSelector Goals
-   Available AI goals can be found
    [here](http://xikage.elseland.net/mythicmobs/doku.php/databases/mobs/aigoals).
-   **Tutorial is available
    [here](http://xikage.elseland.net/mythicmobs/doku.php/databases/mobs/customai).**

##### Mob Factions

-   Mobs can now be marked with a **Faction** attribute
-   Mob AI controls include new custom Pathfinder goals to make mobs
    attack other mobs that are not in the same faction
-   Mobs in the same faction will never attack each-other.

##### Threat Tables

-   Added Threat Tables
-   Added Mob option **UseThreatTable**, defaults to **false**.
-   Added config.yml option for disabling Threat Tables entirely.
-   Added onEnterCombat, onDropCombat, and onTargetChange triggers for
    mobs with threat tables enabled.

Mobs with Threat Tables enabled will behave more like mobs in RPG games.
Each player in combat with the mob has a threat value based on their
damage done to the mob, and the mob will target the player who has done
the most damage to it (allowing for roles like "tanks").

Threat diminishes for players who are out of line-of-sight or out of
range of the mob for too long.

The API will include methods for "taunting" and modifying player threat.

#### Mob Options

Added lots of new options...

##### Animals

-   **Options.Age: \[integer\]** - *Sets the mob's age.*
-   **Options.AgeLock: \[true/false\]** - *Locks the mob's age.*

##### Creeper

-   **Options.SuperCharged: \[true/false\]** - *Sets if the creeper is
    supercharged.*

##### Ocelots

-   **Options.Tameable: \[true/false\]** - *Determines whether the mob
    can be tamed.*

##### Pig

-   **Options.Saddled: \[true/false\]** - *Sets if the pig is saddled.*

##### Pig Zombies + Variants

-   **Options.Angry: \[true/false\]** - *Determines whether the mob
    starts out as angry or not.*

##### Silverfish

-   **Options.PreventBlockInfection: \[true/false\]** - *Prevents block
    infection, should actually work now...*

##### Snowman

-   **Options.PreventSnowFormation: \[true/false\]** - *Keeps the mob
    from forming snow.*

##### Wolf

-   **Options.Angry: \[true/false\]** - *Determines whether the mob
    starts out as angry or not.*
-   **Options.Tameable: \[true/false\]** - *Determines whether the mob
    can be tamed.*

##### Zombies + Variants

-   **Options.ReinforcementsChance**: can be a number between 0 and 1.0
    with 1 being a 100% chance to spawn reinforcements on taking damage.

#### Effects

-   Added **EntitiesInRadius:radius:radiusY** option for effect targets
-   Added **ThreatTargets** option for effect targets

#### Skills

##### New Triggers

-   Added **\~onInteract** - Fires when a player right-clicks the mob
-   Added **\~onEnterCombat** - Fires when a mob enters combat.
    *(Requires ThreatTables to be enabled)*
-   Added **\~onDropCombat** - Fires when a mob drops combat. *(Requires
    ThreatTables to be enabled)*
-   Added **\~onTargetChange** - Fires when a mob changes targets.
    *(Requires ThreatTables to be enabled)*

##### New Skills

-   Added **AIRunGoalSelector** skill - Modifys the mob's AI Goal
    Selector with the given string

\- airungoalselector 'AI STRING'

-   Added **AIRunTargetSelector** skill - Modifys the mob's AI Target
    Selector with the given string

\- airuntargetselector 'AI STRING'

-   Added **Disguise** skill - Changes the mob's disguise, uses the same
    format as the Disguise option

\- disguise \[disguise\_string\]

-   Added **Jump** skill - Makes the mob jump

\- jump \[vertical\_strength\]:&lt;horizontal\_strength&gt;

-   Added **Leap** skill - Makes the mob leap through the air to its
    target.

\- leap

-   Added **Volley** skill - Fires a volley of arrows

\- volley
\[\#\_of\_arrows\]:\[arrow\_speed\]:\[arrow\_spread\]:&lt;fire\_ticks&gt;

##### Skill Changes

-   Damage skill will now target non-player entities if the mob's target
    is that entity.
-   DamageAll will now behave as expected if radius is 0.

#### Spawners

-   Added **/mm s resettimers \[name\]** command to reset cooldown and
    warmup timers

#### API

-   Added MythicMobSpawnEvent

#### Bug Fixes/Other

-   Fixed a bug where MythicMobs would not always activate skills when
    attacking other MythicMobs.
-   Fixed bug with \~onAttack skills causing recursion when using
    damage-causing abilities
-   Fixed a bug that caused the onExplode trigger to not always work
-   Fixed some bugs with the preventSuicide option not retaining mob
    data after preventing a the mob's death
-   Fixed a bug with projectile skill causing projectiles to not always
    do the configured damage
-   Fixed a couple NullPointerExceptions

### v1.0.0 Release

#### Disguises

-   Added zombievillager, babyzombievillager disguises
-   Disguises will now obey any display-related options that are
    configured for the mob.
-   It does not include any options that include mob power or
    functionality (except horse armor)
-   This includes the Horse, Ocelot, Sheep, and Villager disguises

#### Horses

-   Added HorseCarryingChest option for horses

#### Bugs/Other

-   ShootPotion now uses ticks instead of seconds, in order to be more
    consistent with other similar skills
-   Fixed a bug with the ActivateSpawner skill not working with spawner
    groups
-   Fixed a bug with the new SafeSpawnLocation algorithm

### v1.0.0-RC3

#### Skills

-   Added RemoveSelf skill

#### Spawners

Most spawner commands can now accept wildcards in the spawner name:

-   Wildcards can be ? for a *single-character* wildcard, \* for *any
    number* of wildcard characters.
-   i.e. Running the command **/mm s set T\* leashrange 32** will set
    the leash range to 32 on all spawners starting with T
-   i.e. Running the command **/mm s set ?at leashrange 32** will set it
    on spawners named Cat, Rat, Fat, but not one named Matt
-   if you run a spawner command with \* as the name it will be run on
    ALL spawners.

#### Bugs/Other

-   More performance optimizations
-   Added error checking for a couple systems
-   Better compatibility with various Forge modpacks and modded Bukkit
    servers
-   Fixed a bug with timer skills occasionally throwing a
    ConcurrentModificationException in the console
-   Fixed a bug with RandomSpawns rarely throwing a NullPointerException
    in the console
-   Fixed RemoveMobs skill to unregister mobs from plugin before
    removing them
-   Fixed a rare bug with the MovementSpeed mob option
-   Fixed spawners to spawn mobs in the center of the target block
-   Fixed spawners so that they will measure a mob's height and choose
    an appropriate spawn location rather than spawning mobs in areas too
    short for them to survive
-   Fixed a bug where negative Damage Modifiers were not healing the mob
    as intended
-   Fixed Damage ability to correctly register from the using mob
-   Fixed health ranges in skills not working when smaller health amount
    is put first
-   Fixed spawners spawning mobs underground in some scenarios
-   Fixed player disguises to allow color codes in the names
-   Fixed a bug where damage skills that ignore armor could "multi-kill"
    players that had already just died, causing them to drop their items
    when a plugin such as DeathControl should have prevented it.

### v1.0.0-RC2

#### General

-   More performance optimizations!
-   Updated to support Bukkit 1.7.10
-   Added Debugging Mode, activated using **/mm debugmode true**.
    Currently debug mode disables random spawning, mob spawners, and a
    few other "random" things that would make high-level debugging
    otherwise impossible due to console spam.
-   Added TestEffect and TestSkill utility commands that allow you to
    run effect strings and skill strings from within the game with you
    as the "mob" and your target block as the default target. (example:
    **/mm u testeffect *target lightning*** would run the lightning
    effect on your target)

#### Disguises

-   Player disguise can now specify skin and player name independently
    using the syntax **Disguise: player:playername:skinname**. This
    requires LibsDisguises build 314 or greater.
-   Added **Enderman:&lt;held\_item\_name&gt;** disguise
-   Added **Skeleton** disguise

#### Skills

-   The ActivateSpawner skill can now accept a spawner group to activate
    in the format **g:groupname**

#### Effects

Added new effect targets:

-   Location: effect targets a specific location in the world

**- effect location:\[x\],\[y\],\[z\] (effect)**

-   Spawner: effect targets a spawner

**- effect spawner:\[spawner\_name\] (effect)**

This can also target spawner groups using the format
**spawner:g:\[group\_name\]**

#### API

-   Added getMobLevel(), getNumberOfPlayerKills() methods to
    MythicMobDeathEvent

#### Bug Fixes/Other

-   Fixed a crippling bug with spawners that had a radius of 0.
-   Fixed a bug with spawn radius logic.
-   Fixed the following spawner commands to be usable from the console
    or command blocks: activate, info, and set.
-   Fixed a bug where mobs were throwing the death event and granting
    players XP after being removed by the **/mm m kill** and **/mm m
    killall** commands
-   Fixed a bug where mobs were still registered as active for a short
    time after dying
-   Fixed a bug where passive mobs were not being unregistered from
    spawners when removed by commands
-   Fixed dropped\_item disguise, usage i.e. Disguise: item:diamond
-   Fixed several bugs preventing mobs from sometimes not despawning
    after a server restart when Despawn was set to true
-   Fixed a bug with compatibility mode causing multiple mounts to spawn

### v1.0.0-RC1

#### New Mob Options

-   **PreventMobKillDrops: (true/false)** - *Prevents mobs killed by
    that MythicMob from dropping loot*

#### New Disguises

-   Added **slime:\[size\]** and **magmacube:\[size\]** disguises

#### Bug Fixes/Other

-   Fixed error with Target distance conditions caused by players
    teleporting to another world
-   Fixed bug where spawners with radius set to 0 would not spawn mob on
    top of the spawner as intended
-   Fixed a number of possible holes that could have potentially lead to
    mobs losing their disguises
-   Updated CachedMobs file to save mob's level for better consistency
    between server restarts when using mob levels
-   Fixed an error caused by having question marks in mob names
-   Fixed the Wither Skeleton disguise
-   Fixed spawn radius not being set correctly and throwing errors upon
    new spawner creation

### Beta Release v0.12.0

#### Massive Performance Boost

v0.12.0 has had a lot of components optimized for better speed, and most
large servers that have complex mobs should see a noticeable TPS gain.

#### New Features

##### Drop Conditions

All conditions can now be used in drop tables using the following
format: &lt;`>
SandSkeletonDrops:
  Conditions:
  - biome BEACH
  Drops:
  - WaterloggedArmor 1 0.01
<`&gt;

##### Item Lore Improvements

-   You can now specify a number range in item lores, such as
    **{5-10}**, that will come out as a random number in that range when
    the item is generated.

#### New Configs

Added the following configs to **config.yml** for some better
compatibility with certain plugins: &lt;`>
compatibility:
  heroes-show-xp-message: true
  heroes-xp-message-format: You receive $xp experience for slaying $mobname
  mcmmo-show-xp-message: true
  mcmmo-xp-message-format: You receive $xp experience for slaying $mobname
  skillapi-show-xp-message: true
  skillapi-xp-message-format: You receive $xp experience for slaying $mobname
  vault-show-money-message: true
  vault-money-message-format: You receive $money for slaying $mobname
<`&gt;

#### Plugin Compatibility

##### Lib's Disguises

Using Lib's Disguises + ProtocolLib together with MythicMobs unlocks the
**Disguise** mob option. This allows you to disguise any mob as another
entity, including **players**, **falling blocks**, **items**, and
**minecarts**. This effectively allows you to create player mobs and
hostile fauna (example: disguising a zombie as a cow, so you end up
having a cow attacking things).

&lt;`>
AngryPig:
  Mobtype: pigzombie
  Display: 'Angry Pig'
  Health: 30
  Damage: 5
  Options:
    Disguise: pig
<`&gt;

##### EffectsLib

Several new effects have been added that require EffectsLib to be
installed.

##### McMMO

McMMO is now supported!

Mobs can give McMMO experience as a drop in drop tables using the format
**mcmmo-exp \[amount\]**

#### New Skills

-   CommandRing - *Executes a command for all players within a "ring"
    around the mob*

\- cmdring min\_radius:max\_radius:'command'

#### New Skill Triggers

-   **\~onPlayerKill** - *Triggers when the mob kills a player.*

#### New Mob Options

-   HorseSaddled: (true/false)
-   HorseArmor: (iron/gold/diamond)

#### New Spawner Options

-   HealOnLeash (true/false) - *If true, mobs will heal to full upon
    being leashed by a spawner*
-   SpawnRadius - *Spawn Radius already existed, but it should actually
    work now!*

#### New Effects

-   ParticleRing - *Creates a ring of particle effects consisting of
    **ring\_points** points around the target with radius
    **ring\_radius***

\- effect boss particlering
particle\_name:ring\_radius:ring\_points:horizontalspread:verticalspread:count:&lt;speed&gt;:&lt;y-offset&gt;

-   ParticleSquare - *Creates a square of particles around the target
    with radius **square\_radius***

\- effect boss particlesquare
particle\_name:square\_radius:horizontalspread:verticalspread:count:&lt;speed&gt;:&lt;y-offset&gt;

#### New Conditions

-   haspotioneffect \[potion\_effect\]:&lt;level\_number\_range&gt;
-   holding \[material\]
-   inblock \[material\]
-   lightlevel \[number\_range\]
-   lightlevelabove \[integer\]
-   lightlevelbelow \[integer\]
-   mobtype \[list,of,bukkit,mob,types\]
-   playerkills \[number\_range\] - *matches the number of players the
    mob has killed*

#### Bug Fixes/Other

-   MobType is now case-insensitive
-   You can now use the notation **mobname:level** when creating
    spawners
-   Rewrote a large part of the item and drop-table systems for better
    performance and to add new features
-   Added support for splitting Heroes XP based on Heroes' party system
-   Fixed variables not being processed in $mobname inside of message
    skills
-   Fixed mob tracker to correctly track mobs with their level in their
    display name after a server restart.
-   Fixed moblevel attribute not saving on spawners
-   Fixed a ConcurrentModificationException error being thrown by
    certain Timer skills
-   Fixed errors with the Rally skill when the mob didn't have a proper
    target
-   Fixed a bug with null lore in certain items
-   Fixed a recursion bug involving mounts and compatibility mode
    spawning multiple mounts
-   Fixed a bug in the Summon skill's positioning logic
-   Fixed a bug with Mythic Spawners where the Warmup timer did not
    persist through reloads
-   Fixed height condition
-   Fixed level condition
-   Fixed an error thrown when a mob type isn't specified in the **/mm
    mob spawn command**
-   Fixed null pointer error thrown in ChunkUnloadEvent
-   Fixed null pointer error thrown in EntityDeathEvents
-   Fixed dashes displaying properly in mob strings
-   Fixed spawning mobs at specific location using command not working
    in some cases
-   Delayed skills will now execute after a mob dies if the \~onDeath
    trigger was used. **This does mean it is possible to put strain on
    your server with an infinite loop if you have an \~onDeath skill
    call itself, so doing that isn't a good idea.**

### Beta Release v0.11.1

Streamlined string parsing so all mob variables are usable in all skills
and places where variables are used including in mob names in most
cases.

#### New Variables

-   Added $mobuuid variable to mob names and messages

#### New Conditions

-   mobsinchunk \[number\_range\]
-   mobsinworld \[number\_range\]
-   targetdistance \[number\_range\]

#### Bug Fixes/Other

-   RandomSpawning should now obey WorldGuard mob-spawning flags
-   Fixed $level variable in names and messages
-   Fixed drops being dropped twice
-   Fixed DropsPerLevel not working
-   Fixed an error being thrown by mob levels in random spawns
-   Fixed projectiles hitting mobs when fired from a dispenser throwing
    an error
-   Fixed the GCD and SetStance skills
-   Fixed the Equip skill
-   Fixed the biome and world conditions matching similar-but-different
    biomes and worlds
-   Reduced the overhead of update checking significantly

### Alpha Release v0.11.0

#### New Features

##### Skill Conditions

-   Conditions can now be specified for meta-skills. Skills with
    conditions will only be used if the conditions are all true. Skills
    can use all the same conditions as spawners and random spawning
    (although ones that don't necessarily make sense for skills will not
    work so well).
-   Conditions are specified in the Conditions tag in meta-skills like
    so:

&lt;`>
SmashAttack:
  Cooldown: 8
  Conditions:
  - targetwithin 25
  Skills:
  - msg 50:'$boss; &4Diiiie!' >0 0.2
  ...
<`&gt;

##### Mob Levels

-   Added **Mob Levels**. Mobs can now be spawned with a level, and will
    scale based on configurable settings using the **LevelModifiers**
    options. Drops will also be scalable using the DropsPerLevel tag,
    and I may also add a way to have certain drops only drop if the mob
    is above a certain level.

Spawners can spawn mobs of different levels by setting the spawners'
**moblevel** attribute. Mobs can also be spawned with commands by
appending :level to their name, such as **/mm mob spawn
SkeletalKnight:5**

Random Spawning also supports mob levels using the Level option. &lt;`>
SkeletalKnight:
  Mobtype: witherskeleton
  Display: '&2Skeletal Knight'
  Health: 40
  Damage: 8
  Drops:
  - GOLD_NUGGET 2 0.5
  DropsPerLevel:
  - GOLD_NUGGET 1 0.5
  LevelModifiers:
    Health: 5
    Damage: 0.5
<`&gt;

-   **Important Note:** The **LevelModifiers.Health** attribute is
    REQUIRED to use mob scaling. All other modifiers are optional.

##### Special Characters

The Message skill, SetName skill, and display names now support more
special charcters:

-   : makes a colon **:**
-   ' makes an apostrophe **'**
-   ‐ makes a dash **-**

and some other random HTML characters to find...

#### New Mob Types

-   **pigzombievillager**
-   **babypigzombievillager**
-   **angrypigzombievillager**
-   **angrybabypigzombievillager**

#### New Skills

-   **GCD** *Sets the mob's **Global Cooldown** variable for \# ticks,
    usable with the **offgcd** skill condition.*

\- gcd \[ticks\]

-   **SetName** *Changes the mob's display name. Can use all the same
    variables as the message skill.*

\- setname '$mobname ($level) $mobhp/$mobmaxhp'

-   **SetStance** *Sets the mob's **stance** variable, usable with the
    **stance** skill condition.*

\- setstance \[string\]

-   **Rally** *Causes all nearby entities of the specified types to
    attack the mob's target. Types can also be the name of a MythicMob.*

\- rally \[horizontal\_radius\]:\[vertical\_radius\]
&lt;mobtype1&gt;,&lt;mobtype2&gt;

#### New Conditions

-   biome \[biome1\],&lt;biome2&gt;,&lt;biome3&gt;, ...
-   offgcd *whether or not the mob's global cooldown variable is up,
    which can be triggered with the **gcd** skill*
-   height \[number\_range\]
-   heightabove \[integer\]
-   heightbelow \[integer\]
-   level \[number\_range\]
-   onblock \[material\_type\] *must use material name as defined in
    Bukkit*
-   stance \[string\] *variable usable with the **setstance** skill,
    default stance is **default***
-   targetinlineofsight
-   targetnotinlineofsight
-   targetwithin \[integer\]
-   targetnotwithin \[integer\]
-   world \[world1\],&lt;world2&gt;,&lt;world3&gt;, ...
-   worldtime \[number\_range\]

*\[number\_range\] can be numbers such as =10, &gt;10, &lt;15 or a range
such as 1-20*

#### Effects

##### New Effect Position

-   **playersinradius:\#** - *Causes the effect on all players within \#
    blocks*

##### New Effects

-   **particleline** - *Creates a line of particles between the boss and
    the target location with the given parameters. Won't really do
    anything if the target location is set to boss, since the boss
    targeting himself doesn't make much of a line.*

\- effect target particleline
particleName:horizontalSpread:verticalSpread:amount:&lt;speed&gt;:&lt;y-offset&gt;:&lt;particleSpacing&gt;
=HP &lt;chance&gt;

#### Bug Fixes

-   Fixed a bug where abilities would trigger sooner than intended
-   Fixed an issue on 1.7.9 where zombies would sometimes spawn as baby
    zombies

### Beta Release v0.10.8

-   Added support for 1.7.9
-   Various minor bug fixes

### Beta Release v0.10.5

**Notice: This build introduces a lot of performance changes and tweaks.
I recommend testing this before uploading it to your live server.**

#### Performance Changes

This update includes a lot of performance tweaks and some new options to
help servers that are suffering from lag since v0.10 was released. The
recent additions of timer skills and my new mob scanner, which prevents
mobs from ever losing their skills and drops, have added a lot of
overhead, so I've gone ahead and made some drastic changes aimed at
increasing performance.

I've added the following two options to config.yml:

-   **general.clock-interval** - *Controls the speed (in ticks) of
    MythicMobs' internal clock. Defaults to 1 (every tick). Changing
    this requires a plugin restart. Recommend increasing this in
    increments of 5.*
-   **general.scanner-interval** - *Controls how often (in seconds)
    MythicMobs will scan the world to reconcile or despawn Mythic Mobs
    that have forgotten who they are. Defaults to 20 seconds.*

**clock-interval** will NOT affect how often timers, spawners, etc. go
off contrary to what I may have previously said in comments, as I have
added a fix for this. However, if you set clock-interval higher, timers
that are set up to go off more frequently then the clock will not go
often as much as intended, as the clock does not have the precision to
set them off that often. I do not recommend setting the clock-interval
above 20 ticks, but it won't really hurt anything if you do, things just
may behave a little strangely.

As a reminder there are also the following options in config.yml people
can tweak for performance:

-   **general.spawns-interval** - *Controls the speed (in seconds) of
    MythicMobs spawners. Changing this will affect the speed of
    spawners' Cooldown and Warmup attributes.*
-   **general.save-interval** - *Controls the speed (in minutes) that
    MythicMobs will save. Defaults to 5.*

#### New Mob Type

-   Added **chickenjockey** mob type. Jockey chickens will not do
    anything special on their own, but if a zombie rides them they will
    attack players.

#### New Mob Options

-   added FuseTicks option - Creepers only. Sets the number of ticks it
    takes a creeper to explode.
-   added ExplosionRadius option - Creepers only. Sets the radius/power
    of the creeper's explosion.

#### Bug Fixes / Other

-   Fixed Heroes EXP, SkillAPI Exp and Vault currency not always being
    granted properly
-   Fixed a rare error message with timer skills
-   Fixed a bug where MythicMobs' mob scanner was going off much more
    often than intended.
-   Various other performance-related tweaks

### Beta Release v0.10.2

-   Fixed a bug where mobs weren't equipping armor

### Beta Release v0.10.1

#### Bug Fixes / Other

-   Changed Timer-based skills to use the mob's target as the skill
    target
-   Fixed amounts and chance to work with all drop types in drop tables
-   Changed amounts in drop tables to allow ranges \#-\# on all drop
    types
-   Fixed debugging not working on startup
-   Fixed a bug involving effects on mob targets
-   Fixed item attributes causing irrelevant errors on startup
-   Fixed mobs not dropping aggro on targets that have already been
    killed
-   Fixed creeper explosion damage not being changed properly
-   Fixed creepers not obeying anti-block-explosion protection

### Beta Release v0.10.0

**Note: This release fixes some bugs with item attributes and changes
the way they are applied to a way that makes more sense. This may impact
your server, if you are worried do some testing first! For example,
setting MovementSpeed to 0.1 will now add +10% Movement Speed rather
than adding +0.1 Movement Speed, which is kind of arbitrary.**

#### New Features

-   Added support for 1.7.5
-   Added support for 1.6.4
-   Added **Skill Triggers**. You can now specify an event trigger in a
    skill using the syntax **\~eventname** before or in place of the
    health modifier. Some triggers ignore the health modifier when it
    makes sense (mainly as onSpawn, onDeath) and a health modifier is
    not required for these. If you do not specify an event, skills will
    continue to work as they did before, *meaning they will fire
    onSpawn, onDeath, onAttack and onDamaged* like they do currently.
    Current triggers include:

\* onSpawn - *called when the mob spawns* \* onDeath - *called when the
mob dies* \* onAttack - *called when the mob deals damage* \* onDamaged
- *called when the mob takes damage* \* onExplode - *called when the mob
explodes (creepers only)* \* onTeleport - *called when the mob teleports
(endermen only)* \* onTimer:\# - *called every \# ticks (does **not**
work in meta-skills)*

So for example, the following creeper would hit everything nearby with
lightning only when exploding: &lt;`>
LightningCreeper:
  Mobtype: poweredcreeper
  Display: '&2Lightning Creeper'
  Health: 40
  Damage: 8
  Options:
    PreventSuicide: true
  Skills:
  - lightningall 6:5 ~onExplode >0 1
  - lightningall 10:1 ~onTimer:40 >0 1
<`&gt;

-   Added **SpawnMethod** attribute to RandomSpawns. Can be **add** or
    **replace**. Defaults to **add**. Add works exactly how random
    spawning works now, by adding new spawns to the world. "replace"
    gives mobs spawning a chance to replace other mobs.'
-   Added SkillAPI Support. You can now use **skillapi-exp \[amount\]**
    as a drop if you have SkillAPI installed.
-   Added MythicDrops Support. You can now use **mythicdrop
    &lt;tier&gt;** as a drop if you have MythicDrops installed.

#### New Mob Options

-   added PreventSuicide option (default false) - Prevents a creeper mob
    from dying upon exploding.

#### New Spawning Conditions

-   dawn
-   day
-   dusk
-   night

#### Bug Fixes / Other

-   Fixed some bugs with Item attributes
-   Certain item attributes now apply as a percent modifier rather than
    as a static value, where it makes sense
-   Implemented additional checks to prevent mobs from losing their
    drops and skills
-   Possibly fixed passive mobs not despawning when Despawn is set to
    true
-   Creepers' explosion yield is now based on their Damage value if one
    is defined
-   Fixed a bug where certain types of mobs wouldn't spawn using random
    spawning
-   Fixed mobs being able to be spawned via command blocks
-   Hopefully fixed a bug where more random spawns were spawning than
    intended (unable to verify myself)
-   Fixed a bug where decimals were not being taken into account in
    cooldowns
-   Fixed a bug where skill cooldowns less than 1 were not registering
    at all
-   Fixed a bug where certain items in drop tables would multiply every
    time a mob was killed
-   Various other bug fixes

### Beta Release v0.9.0

#### New Features

-   Mob Stacks - If one mount isn't enough, you can now stack mobs by
    creating a mob stack:

&lt;`>
SheepStack:
  MobStack: StaticallyChargedSheep,StaticallyChargedSheep,StaticallyChargedSheep,StaticallyChargedSheep
<`&gt;

-   Spawner Group commands - most spawner commands now accept
    **g:groupname** instead of a mob spawner name, and will change all
    spawners associated with that group.
-   Skills can now use a percentage for the health modifier, i.e.
    **=50%** or **&lt;25%** etc
-   Health modifiers now scale with the mob's max health, including
    health granted by gear and health added by mob level scaling (coming
    in a future build). This means if a mob has a max health of 200, and
    a skill is set to fire at =100, then if the mob has 400 health from
    gear or scaling the skill will fire at 200 health. This is necessary
    for mob levels and scaling in the future.
-   You can now use multiple health modifiers per skill, in a
    comma-separated list. So the following skill string is valid:

&lt;`>
- skill dosomething =75%,=50%,<200
<`&gt;

-   Added WorldGuard Support
-   Added **ShowHealth** option to all mobs, and two new config values
    to config.yml - **show-health-radius** and **show-health-format**

Will display a message to all players within the radius every 10% of the
mob's health if ShowHealth is set to true. Format can include color
codes and variables $mobname, $mobhp, $mobmaxhp, and $percent.

#### New Spawner Attributes

-   You can now change the spawner's mob type by setting the **mobtype**
    attribute

#### New Spawning Conditions

WorldGuard conditions, region can be a comma-separated list of region
names:

-   inregion \[region\]
-   notinregion \[region\]

also:

-   inside \[true/false\]

#### New/Updated Skills

-   Added Mount skill
-   Added Dismount skill
-   Added SpawnPassenger skill
-   Added EjectPassenger skill
-   Added MountPlayer skill
-   Added TeleportLocation skill
-   Added RemoveMobs skill
-   Added ToggleLever skill
-   Added SetHealth skill
-   Added SetMaxHealth skill

#### Bug Fixes / Other

-   Mobs should use abilities immediately at the intended health level
    instead of one hit after.
-   Fixed a bug with the spawners/listnear command involving
    multi-worlds
-   Fixed a bug where the Message skill would not display mob health
    correctly.
-   The RepeatAllSkills option should now work as intended.
-   Fixed Ranges in Health modifiers so they work properly.
-   Some refactoring and optimizations here and there.

### Beta Release v0.8.2

#### Bug Fixes

-   Fixed a bug with Vault support

### Beta Release v0.8.1

#### Bug Fixes

-   Fixed a bug with display names losing color codes on death
-   Fixed a bug with Heroes exp
-   Fixed a bug on servers without Vault

### Beta Release v0.8.0

#### New Features

-   Mobs can now have mounts (limit 1 for now)! Using the Riding:
    attribute with the name of another MythicMob, i.e.

&lt;`>
Herobrine:
  Mobtype: witherskeleton
  Display: '&4Herobrine'
  Health: 50
  Riding: MrEd
<`&gt;

Lots of compatibility with other plugins!

-   added BarAPI support
-   added Heroes support
-   added LanguageAPI support
-   added PhatLoots support
-   added Vault support

#### New Skills

-   **BarTimer** *Creates a bar with the specified message, for \#
    seconds. **REQUIRES BarAPI***

\- bartimer \[radius\]:\[seconds\]:'Message' &lt;health&gt;
&lt;chance&gt;

#### New Drop Types

-   added **heroesexp \#** - grants \# XP for Heroes to the killer.
    Requires Heroes.
-   added **phatloot \[phatloot\_name\]** - The boss will generate loot
    from the supplied PhatLoot and drop the items. Requires PhatLoots.
-   added **money \#** - Grants money using Vault. Requires Vault and a
    corresponding economy plugin.

#### New Mob Options

-   added AlwaysShowName option (default false) - Whether to always show
    the mob's display name, or only when it's being looked at.
-   added PreventItemPickup option (default true) - Prevents mobs such
    as zombies from picking up player's dropped items.
-   added PreventBlockInfection option (default true) - Prevents
    Silverfish from infecting stone blocks.
-   added HorseTamed option (default true) - Causes horses to be tamed
    or not.

#### Item Improvements

-   $player and $boss can now be used in item lores, and will show the
    mob's name and the killer's name when the item drops.

#### Bug Fixes

-   Fixed a bug or two with the Damage skill
-   Fixed the Firework and RadiusFirework effects
-   Lots of other bug fixes

### Beta Release v0.7.0

**IMPORTANT: Read information about Item and Drop Table changes below if
nothing else**

#### API

-   Added MythicMobSkillEvent(). Fired whenever a mob executes a Mythic
    Mob skill. This will be called even if the skill does not exist in
    Mythic Mobs, so it can be used to create custom skills.

#### New Features

-   Mythic Spawners can now use spawning conditions just like Random
    Spawns
-   Spawner conditions are added and removed using a few new in-game
    commands, and can be viewed under **/mm s info**

#### New Commands

-   **/mm spawner addcondition \[spawner\_name\] \[condition\]
    \[value\]**
-   **/mm spawner removecondition \[spawner\_name\] \[condition\]**

#### New Spawning Conditions

Should all be self-explanatory... I think. Will add to the plugin manual
soon.

-   lunarphase \[phase\] *(\[phase\] can be a comma-separated list of
    in-game days corresponding to the lunar phase, 0 thru 7)*
-   outside \[true/false\]
-   playerwithin \[distance\]
-   playernotwithin \[distance\]
-   raining \[true/false\]
-   sunny \[true/false\]
-   thundering \[true/false\]

#### Drop Table Changes

I had been trying to use EpicBoss' format for the drop tables and items
drops, but it wasn't really making sense or working out and seemed to
cause a lot of confusion, so I ended up changing a few things. **This
WILL break item configs, so sorry, but it's a beta!**

-   Equipment uses relatively the same format, **- MythicItem:slot
    &lt;amount&gt; &lt;chance&gt;**
-   Drops for MythicItems use a slightly new format: **- MythicItem
    &lt;amount&gt; &lt;chance&gt;**
-   Drop tables using items now use this format: **-
    \[item\_id\]:&lt;data\_value&gt; &lt;amount&gt; &lt;chance&gt;**
-   Experience now uses the format **- exp &lt;amount&gt;**

Chance is an integer between 0 and 1, with 1 being a 100% chance. Amount
can be a number or a range such as 1-20, 30-100, etc.

So this example would drop 100 exp and between 32 and 64 golden nuggets:
&lt;`>
SkeletonKingDrops:
  Drops:
  - 371:0 32-64 1
  - exp 100
<`&gt;

#### Bug Fixes

-   Fixed bug in 0.6.5 that prevents you from creating spawners...
    (oops)
-   Fixed bugs with copied spawners sharing mob tables and not spawning
    new mobs
-   Fixed another bug with exp drops
-   Fixed item amount ranges not being random
-   Fixed a bug with the outside condition not always working

### Beta Release v0.6.5

#### API

-   Added MythicMobDeathEvent() for people looking to hook for
    compatibility.
-   More API stuff to come in the future, pushed this out with bug fixes
    since it was done.

#### New Features

-   You can now use **exp \#** under Drops to add exp to a mob without
    using a drop table.

#### Bug Fixes

-   Hopefully fixed a bug with MythicMob items not playing nicely with
    other plugins, even if you don't add any attributes under "Options"
    on items.
-   Adding attributes to items may still cause them to behave oddly.
    This is because Bukkit has no API for that stuff yet.
-   Fixed some errors with loot drops.
-   Fixed a bug with mobs not dropping the configured amount of exp
-   Fixed some bugs with effects not always firing properly
-   Fixed a bug where spawners would break when using multiple worlds,
    if a world was reloaded.
-   Various other bug fixes

#### Known Issues

-   Amount ranges in Drop Tables do not function as intended
-   Spawners may sometimes spawn an extra mob sometimes after a world
    has been unloaded and reloaded.

### Beta Release v0.6.0

#### New Features

-   Mythic Mob Eggs (access using **/mm eggs** or **/mm e**)
-   Utility Commands (access using **/mm utilities** or **/mm u**)

Only utility command right now lets you easily find the coordinates of
the block you're looking at, for use with the pushbutton skill.

#### New Skills

-   **PushButton** *Pushes a button at the specified coordinates, to
    activate redstone*

\- pushbutton x:y:z

#### New Spawner Attributes

-   LeashRange - Sets a leash range for mob spawners. Mobs that go
    further than the leash range from the spawner will be teleported
    back to the spawner.

#### Bug Fixes / Other

-   Mobs will now use more skills against other mobs, such as wolves
-   Fixed more mob-dupe issues with mob spawners and unloaded chunks.
-   Switched to a better caching format. **You may want to delete and
    regenerate your SavedData/CachedMobs.yml**
-   Skill cooldowns and delays should line up smoother and more
    predictably now.\\
-   Various other bug fixes and optimizations

### Beta Release v0.5.3

#### Bug Fixes

-   Items can now be referenced in most cases by name to prepare for a
    future where item IDs do not exist
-   Fixed a bug where Item Data values were not working (fixes issues
    with player heads)
-   Fixed a few issues that could cause mob spawners to break when the
    chunk unloads.
-   Fixed mobs not using abilities when attacking with bows
-   Fixed some other bugs associated with spawners and unloaded chunks
-   Maybe fixed an issue with slimes splitting when they shouldn't?
    (needs more testing)

### Beta Release v0.5.0

#### Major Features

-   Mythic Mob Spawners (access using **/mm spawners** or **/mm s**)

Mythic Mob Spawners allow you to create "spawners" that will spawn mobs
at a location based on certain conditions. They can work similar to
normal spawners or can be set up just to spawn a boss at a certain with
a long cooldown. They can spawn things using timers, or if you shut the
timer off, just through commands or by other Mythic Mobs using the new
spawner skill.

Typing **/mm spawners** (or **/mm s**) will bring up all the commands
for spawners. After creating a spawner, you can set attributes for it
using **/mm s set \[spawner\_name\] \[attribute\] \[value\]**. Just
typing **/mm s set** will bring up a list of attributes and what they
do.

I will be posting a tutorial for spawners VERY soon, but for server
admins that are savvy, you should be able to figure out spawners using
just the in-game commands and the information they give you.

#### New Skills

-   **Spawner** *Activates a Mythic Mob Spawner*

\- spawner \[name\] =HP &lt;chance&gt;

#### New Mob Setting

-   Added Despawn setting for all mobs.

#### Bug Fixes

-   Added lots of catches for commands to prevent bugs
-   Several fixes to prevent certain mob types (such as Iron Golems)
    that don't despawn from losing their Mythic Mobs skills
-   Various bug fixes

### Beta Release v0.4.0

\*\* Delete example files to get updated ones with this update! \*\*

#### Major Features

*Example configurations are included demonstrating how these work.
Documentation will come in the future.*

-   Damage Modifiers - Allows you to modify how much damage a mob will
    take from certain sources. Will multiply damage from the set source
    by the number you specify.
-   Item Commands (**/mm items**)

The following sheep would take no damage from fire, and 20% damage from
lava: &lt;`>
FireResistantSheep:
  Mobtype: sheep
  DamageModifiers:
    - LAVA 0.2
    - FIRE 0
    - FIRE_TICK 0
<`&gt;

Uses the built-in damage causes. These can be found here:
<http://jd.bukkit.org/rb/doxygen/de/d62/enumorg_1_1bukkit_1_1event_1_1entity_1_1EntityDamageEvent_1_1DamageCause.html>

#### Commands

You can now spawn mobs at a specific x,y,z location using the mobs spawn
command:

-   **/mythicmobs mobs spawn \[amount\] \[world\],\[x\],\[y\],\[z\]**

#### New Options

Added lots of new options for mobs. See included examples...

-   **PreventOtherDrops** - *True/False. Defaults to False. Stops items
    from dropping that aren't configured to drop in Mythic Mobs*
-   **PreventLeashing** - *True/False. Defaults to True. Prevents Mythic
    Mobs from having a leash put on them.*
-   **PreventRenaming** - *True/False. Defaults to True. Prevents Mythic
    Mobs from having their name changed by a name tag.*
-   **RepeatAllSkills** - *True/False. Defaults to False. Setting to
    True will make mobs repeat skills when using a skill with =HEALTH,
    if the mob heals back above that health amount .*
-   **PreventSlimeSplit** - *True/False. Defaults to False. Prevents
    Mythic Mob Slimes and MagmaCubes from splitting on death.*
-   **PreventTeleporting** - *True/False. Defaults to False. Prevents
    Mythic Mobs from teleporting. Mainly meant for Endermen.*

Will add a complete list of mob options soon with the documentation.

#### New Skills

5 new special skills. Adding "all" to the end of these skills will make
them also hit other nearby mobs, in addition to players. Otherwise they
work exactly the same.

-   **damageall**
-   **igniteall**
-   **pullall**
-   **throwall**
-   **lightningall**

#### New Effects

-   **particles** - *Creates a particle effect at the target location
    with the given parameters.*

\- effect boss particles
particleName:horizontalSpread:verticalSpread:amount:&lt;speed&gt;:&lt;y-offset&gt;
=HP &lt;chance&gt;

A list of available particles can be found here until documentation is
done (use the "coding name" for this):
<http://minecraft.gamepedia.com/Particles>

#### Bug Fixes

-   Fixed a bug when trying to spawn a mob without a display name set
-   Fixed a bug with item display names
-   Fixed a bug with item "amount" not defaulting to 1
-   Fixed Slime's health not being set properly
-   Corrected an incorrect item example...
-   Various other bug fixes

### Beta Release v0.3.0

#### Major Features

*Example configurations are included demonstrating how these work.
Documentation will come in the future.*

-   Custom Items
-   Mob Equipment
-   Mob Drops
-   Drop Tables

**Note about Equipment:** While the items function similar to EpicBoss
Gold Edition for the most part, in MythicMobs you are not required to
use drop tables for equipment. You can simply put the name of an item
defined in your items folder under "Equipment" using the format
**ItemName:slot**. You can still use drop tables if you wish, though,
and if a drop table and an item have the same name, it will use the drop
table. In the next few builds I will try to allow you to just put basic
items in the mob config without having to make a custom item at all. .

#### New Skills

*Skills in most cases function identically to the skills used in
EpicBoss Gold Edition. Documentation of these can be found here:*
<http://www.epicboss.empirehostings.net/Support/showthread.php?tid=4551>

-   **Ignite** *sets players in radius on fire for so many ticks. if
    radius = 0, only hits the attacking player*

\- ignite radius:ticks

-   **Equip** *makes the boss equip an item defined in your items
    folder*

\- equip itemname:slot

-   **Explosion** *creates explosions on players in radius on fire for
    so many ticks. if radius = 0, only hits the attacking player*

\- explosion
radius:power:&lt;fire(true/balse)&gt;:&lt;destroyblocks(true/false)&gt;

-   **Weather** *Changes the weather, can be rain, thunder or sunny*

\- weather type:duration

#### Bug Fixes

-   Fixed a last-second bug with Random Spawning conditions

#### Converting from EBGE

To make your EBGE Items and Loots configs work with MythicMobs, you just
have to change the following things:

-   Rename Tags to Options
-   Rename Loots to Drops
-   Rename Lores to Lore
-   Rename Enchants to Enchantments

### Beta Release v0.2.0

#### Major Features

-   Random Spawning system
-   Random Spawning Conditions (only one added so far is the "outside"
    condition, included in an example file)

#### New Skills

*Skills in most cases function identically to the skills used in
EpicBoss Gold Edition. Documentation of these can be found here:*
<http://www.epicboss.empirehostings.net/Support/showthread.php?tid=4551>

-   ForcePull
-   ForcePullNear
-   NewTarget
-   Potion
-   PotionBoss
-   PotionMobs
-   Pull
-   RandomSkill
-   ShootFireball
-   ShootPotion
-   Projectile
-   ShootSkull

#### New Effects

-   endersignal

\- effect boss endersignal =HP &lt;chance&gt;

-   firework

\- effect boss firework
&lt;type&gt;:&lt;colors&gt;:&lt;fadecolors&gt;:&lt;flicker&gt;:&lt;trail&gt;:&lt;flightduration&gt;
=HP &lt;chance&gt;

-   flames

\- effect boss flames =HP &lt;chance&gt;

-   lightning

\- effect boss lightning =HP &lt;chance&gt;

-   smoke

\- effect boss endersignal =HP &lt;chance&gt;

-   radiusfirework

\- effect boss radiusfirework
&lt;type&gt;:&lt;colors&gt;:&lt;fadecolors&gt;:&lt;flicker&gt;:&lt;trail&gt;:&lt;flightduration&gt;
=HP &lt;chance&gt;

#### Other Stuff

-   Added Metrics

### Beta Release v0.1.0

First public development release!

#### Major Features

-   Creating Mobs
-   Mob skills and creating "Meta" Skills
-   Start of the Effects system

#### Coming Soon

-   Custom mob spawners
-   Items or equipment
-   Locations
-   Random spawning
-   Spawning eggs
-   Timers

Skills in most cases function identically to the skills used in EpicBoss
Gold Edition. Documentation of these can be found here:
<http://www.epicboss.empirehostings.net/Support/showthread.php?tid=4551>

Differences in MythicMobs from EBGE include:

-   The health and chance fields in skills are OPTIONAL, if you leave
    them out they will fire 100% of the time
-   Boss attributes are called "options" instead of "tags"

#### Skills

-   command (or cmd)
-   consume
-   damage
-   damageself
-   effect
-   healself (or heal)
-   lightning
-   message (or msg)
-   radiuscommand
-   skill (aka "pack" or meta skills)
-   suicide
-   summon (aka swarm)
-   teleport
-   teleportnear
-   throw

#### Effects

-   sound
-   explosion

#### Mob Options

All options/tags from EBGE should work, let me know if I missed one. The
list of them can be found here:
<http://www.epicboss.empirehostings.net/Support/showthread.php?tid=4548>

#### Feedback is Appreciated!

Please provide all bug-related feedback through tickets and suggestions
through the forums.
