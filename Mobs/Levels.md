Mob Levels
==========

<img src="http://fs5.directupload.net/images/160306/uozz9rdv.jpg" width="500" height="250" alt="http://fs5.directupload.net/images/160306/uozz9rdv.jpg" />

This is a database of all Options available for Mob Levels.

Mob levels are a useful function for adding levels to your mob. Adding
levels to your mob can allow for several different things.

You can have their damage and hitpoints scale up as their level
increases, you can have them drop more items depending on what their
level is (see _BonusLevelItems_ in [Droptable Options](/Items/Drops#droptable-options)).

Or, for more advanced configs you could change their drops completely
depending on what level they are, give them different skills depending
on their level, or even change where/how they spawn depending on what
level they are (using spawners and randomspawns.)

Mob levels can be influenced by world scaling (see below), [Random
Spawners](/Random%20Spawns) or the [SetLevel
mechanic](/skills/mechanics/setlevel).

This page will only be covering the basics, a future guides/examples
section may include more in-depth tutorials later on.

    Zombie:
      MobType: zombie
      Health: 100
      Damage: 10
      Display: '&5Zombie Lvl - <mob.level>'
      Options:
        MovementSpeed: 0.3
      Drops:
      - myDroptable
      LevelModifiers:
        Health: 5
        Damage: 0.5
<!--
DropsPerLevel
-------------

The drops listed under this section will be applied depending on the
level of the mob. In the example above the Zombie has a 50% chance of
dropping an additional gold nugget per level. So if he's level 5 he has
a chance to drop up to 6 gold nuggets.

See [Drops Overview](/databases/drops/overview) for more information.

*DropsPerLevel has been removed as of v4.4*
-->
LevelModifiers
--------------

These options, put under the LevelModifiers section, will increase the
mobs respective stats by the given numbers per level. These stats will
be added on top of their base stats.

Level modifiers may not work if you didn't specify specify base values
for the affected attributes in the mob configuration.

      * **Health: [number]**
      * **Damage: [number] ((The damage value will never influence the damage dealt by potions (witches) or arrows (skeletons) ))**
      * **KnockbackResistance: [number]**
      * [[databases:skills:power_level|Power]]**: [number]**
      * **Armor: [number]**
      * **MovementSpeed: [number]**
      * **AttackSpeed: [number]**

*"MovmentSpeed" and "AttackSpeed" were added in version 2.3.2.*

World Scaling
-------------

Mob levels (for random-spawned mobs) can automatically be set by the
plugin for by specifying world scaling settings in the config.yml
located in */MythicMobs*/. Setting it up is simple. By the default the
section for scaling in your config.yml should look something like this:

      Scaling:
        Default:
          Enabled: false
          PerBlocksFromSpawn: 250
        world2:
          Enabled: false
          PerBlocksFromSpawn: 250
        world2_nether:
          Enabled: false
          PerBlocksFromSpawn: 100

First off, when configuring world scaling for your world, you must
define the name of your world. In most cases and if you didn't apply a
custom name to the folder of your world, that will just the *world*. For
the sake of example, let's say your world is called *MyAwesomeServer*.
As next step, you must set **Enabled: true**.

Now for the important part; setting **PerBlocksFromSpawn: \[blocks\]**.
Based on this value, MythicMobs will make the mobs spawn on different
values. In the example below it is set to **PerBlocksFromSpawn: 250**,
which will make the mobs spawn:

-   **At level 0 in the white area** (0-249 blocks from spawn)
-   **At level 1 in the skin area** (250-499 blocks distance)
-   **At level 2 in the yellow area** (500-749 blocks distance)
-   **At level 3 in the orange area** (750-999 blocks distance)
-   **At level 4 in the red area** (1000-1249 blocks distance)
-   **At level 5 ...** (1250-1499 blocks distance)

![](http://fs5.directupload.net/images/160317/ebnd74rs.jpg)

These options will automatically be applied to all mobs that are
summoned into the game using MythicMobs' [Random
Spawning](/[[databases/spawners/randomspawners). You can use the
**UseWorldScaling: \[true/false\]** option on your randomspawn
configurations to control whether mobs are supposed to be affected by
world scaling.

Note that world scaling options will never affect mobs in
*VanillaMobs.yml* located in */MythicMobs/Mobs*. Vanilla overrides
cannot be affected by world scaling at all. It will only work on custom
mobs created in their own configuration files.
