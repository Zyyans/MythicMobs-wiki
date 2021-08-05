Mobs
====

<img src="http://fs5.directupload.net/images/160306/bpdp2375.jpg" width="500" height="125" alt="http://fs5.directupload.net/images/160306/bpdp2375.jpg" />

MythicMobs is based all around customized entities/mobs and there are
plenty of options, attributes that you can utilize. Below you find a
complete list of options/attributes that can be added to your custom
creations.

Most of them are optional, meaning you don't have configure the entire
list every time you are creating a new mob. All that really is required
are the *internal\_mobname* and the *Type*.

You can make any number of files in the Mobs folder, and they can be
named anything you like as long as the file ends in common document formats(.txt .yml etc).

    internal_mobname:
      Type:
      Display:
      Health:
      Damage:
      Armor:
      BossBar:
      Faction:
      Mount:
      Options:
      Modules:
      AIGoalSelectors:
      AITargetSelectors:
      Drops:
      DropsPerLevel: (Below v4.4 only)
      DamageModifiers:
      Equipment:
      KillMessages:
      LevelModifiers:
      Disguise:
      Skills:
      Trades:

Breaking down the options
-------------------------

**internal\_mobname:**

-   This string will be how your mob will be referenced internally in
    MythicMobs and can be any name you like.
-   Must be alphanumerical and is case sensitive.
-   Examples:
    -   **super\_zombie:**
    -   **SuperZombie:**
    -   **superzombie:**
    -   **SuPeRzOmBiE:**


**Type: \[mobtype\]**

-   This field determines which mobtype your creation will be based
    upon.
-   Complete list of available entities: [Mob
    Types](/databases/mobs/types)
-   Examples:
    -   **Type: zombie**
    -   **Type: SKELETON**

**Display: '\[display\_name\]'**

-   Sets the display name of the mob that will appear as the mobs name
    tag above it's head.
-   Supports color codes and string variables:
    [Variables](/skills/stringvariables)
-   Must be encased by single quotes.
-   For using single quotes inside of the name, you can use the
    &lt;&sq&gt; variable.
-   Examples:
    -   **Display: 'Super Zombie'**
    -   **Display: '&eSuper Zombie'**
    -   **Display: '&cSuper Zombie&r - &lt;mob.level&gt;'**

**Health: \[number\]**

-   Sets the max health of the mob.
-   MythicMobs doesn't have any limitations on max health. Spigot
    however, will by default cap max health at "2048". This can easily
    be changed in the spigot configuration file *spigot.yml*.
-   Examples:
    -   **Health: 200**

**Damage: \[number\]**

-   Sets the base melee damage of the mob.
-   1 damage = 0.5 hearts. Thus a mob with 6 damage will deal 3 hearts
    of damage.
-   This attribute will never affect damage done by ranged attacks, like
    arrows or potions. It's only meant for melee damage.
-   Examples:
    -   **Damage: 10**

**Armor: \[number\]**

-   Will reduce any damage the mob takes by the specified amount.
-   1 damage = 0.5 hearts.
-   Examples:
    -   **Armor: 7**
-    Please note, the Armor stat is currently not working on both free and premium builds.
-    As a work around, add 5HP to the mob's Health stat for each point of Armor

**BossBar:** (2.4)

-   Defines and controls the healthbar of the mob. Looks like the
    Enderdragon's and Wither's health bar, but is configurable in
    appearance. See [BossBar](/databases/misc/bossbar).

**Faction: \[name\]**

-   Sets the faction of the mob, which can be used for advanced AI
    configurations.
-   Must be alphanumerical and is case sensitive.
-   Examples:
    -   **Faction: SuperZombies**
    -   **Faction: super\_zombies**

**Mount: \[internal\_mobname\]**

-   Sets the mount of your mob, must be another MythicMob.
-   The mob will automatically ride on the defined mount when it spawns.
-   Examples:

<!-- -->

        * **Mount: super_zombie_horse**

**Options:**

-   This is a special field which comes with numerous sub-options, like
    determining if the mob should despawn, setting knockback resistance,
    follow range, movement speed and many many more!
-   A complete list of all available options: [Mob
    Options](/databases/mobs/options)

**Modules:**

-   This field allows you to add sub-options that are used to enable
    [Threat Tables](/databases/mobs/modules/threattables) and/or
    [Immunity Tables](/databases/mobs/modules/immunitytables).

**AIGoalSelectors:**

-   This field is used to customize the AI goals of the mob.
-   [Custom AI](/Mobs/AI#goal-selectors)

**AITargetSelectors:**

-   This field is used to customize the AI targets of the mob.
-   [Custom AI](/Mobs/AI#target-selectors)

**Drops:**

-   Used to add custom drops to your mob.
-   Can be vanilla items, mythic items, experience points, cross-plugin
    items (if supported) or even custom drop tables with their own
    condition system.
-   See [Drops Overview](/Items/Drops) for more
    information.
<!--
**DropsPerLevel:**

-   Drops per level work just like regular drops, but the amount of
    drops will increase in a linear relation to the level of the mob.
-   This field is also covered in [Drops
    Overview](/databases/drops/overview). Mob levels are covered in [Mob
    Levels](/databases/mobs/levels).
-   This option was removed in 4.4; please use BonusLevelItems in drop
    tables instead.
-->
**DamageModifiers:**

-   This field allows for full control over how and how much damage
    takes by which causes.
-   For example can be used to make the mob immune to melee attacks, but
    very weak to ranged attacks.
-   See [Damage Modifiers](/Mobs/DamageModifiers) for a
    complete list of options.

**Equipment:**

-   Used to equip the mob with vanilla items or mythic items upon its
    initial spawn.
-   See [Equipment](/Mobs/Equipment) for a complete list of
    options.

**KillMessages:**

-   Allows you to customize the broadcasted kill messages that appear
    when a mob kills a player.
-   [Custom Kill Messages](/Mobs/KillMessages)

**LevelModifiers:**

-   MythicMobs can have levels and this field is used to determine which
    kinds of statistics they should gain on which level.
-   [Mob Levels](/Mobs/Levels)

**Disguise:**

-   This field requires the plugin "LibsDisguises" to be installed and
    functioning on your server.
-   Used to make mobs appear like other entities.
-   [Add-on: Disguises](/Mobs/Disguises)

**Skills:**

-   The skills section is used to determine which skills the mob can
    utilize and when it will do so.
-   See [Skills Overview](/Skills/Start) to get started on making your
    own skills.

**Trades:**

- Allows you to customize villager trades. Villagers must have certain professions to be able to trade, and some items may require the villager to be a certain level. If you want to use MMOItems in villager trades, use `mmoitems.TYPE.ID`. 
```
MerchantTest:
  Type: VILLAGER
  Display: '&6Merchant Test'
  Health: 20
  Faction: tester 
  Options:
    Profession: CLERIC
    Type: DESERT
    Level: 2
  Trades:
    1:
      Item1: 5 EMERALD
      Item2: 5 DIAMOND
      Result: DIAMOND_SWORD
      MaxUses: 5
    2:
      Item1: 64 EMERALD
      Result: mmoitems.SWORD.CUTLASS
      MaxUses: 1
```

Example with all options used
-----------------------------

More mobs can be found in the [Examples](/examples) section.

Please keep in mind that you in no way have to use all of these mob
options and that this is an advanced example designed to show the
possibilities. All that you need to apply is whatever you want for you
mob. The only required options/attributes are the internal-mobname and a
mob-type. After that it's completely up to you.
```
    super_zombie:
      Type: zombie
      Display: '&lSuper Zombie&r'
      Health: 200
      Damage: 14
      Armor: 10
      Faction: superb_zombies
      Mount: super_zombie_undead_horse
      Options:
        PreventOtherDrops: true
        PreventItemPickup: true
        Despawn: false
        KnockbackResistance: 0.25
        MovementSpeed: 0.25
      Modules:
        ThreatTable: false
        ImmunityTable: true
      AIGoalSelectors:
      - 0 clear
      - 1 meleeattack
      - 2 randomstroll
      AITargetSelectors:
      - 0 clear
      - 1 attacker
      - 2 players
      Drops:
      - diamond 1-3 1
      - exp 50 1
      - super_zombie_sword 1 1
      DropsPerLevel:
      - rotten_flesh 1-3 0.5
      - exp 10 1
      DamageModifiers:
      - ENTITY_ATTACK 0
      - PROJECTILE 1.25
      - MAGIC 1.75
      Equipment:
      - super_zombie_helmet:4
      - super_zombie_sword:0
      KillMessages:
      - '<target.name> was superbly slain by a <mob.name>'
      LevelModifiers:
      - Armor 0.05
      - MovementSpeed: 0.01
      - KnockbackResistance: 0.05
      - Health: 2
      - Damage: 1
      Disguise:
        Type: player
        Skin: '&lSuper Zombie&r'
        Player: jaylawl
      Skills:
      - throw{v=5;vy=5} @target ~onAttack 0.5
      - effect:sound{s=mob.zombie.hurt;v=1;p=0} @self ~onDamaged
      - effect:particles{p=cloud;a=50;s=0.05} @self ~onDeath
```