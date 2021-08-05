Drops and Drop Tables
=====================

![](http://fs5.directupload.net/images/160308/p4f6hk8e.jpg)

The Drops tag can be added to your custom mobs to allow them to drop items of your choice upon their death. There are three types of custom drops available in MythicMobs to distinguish between.

You can make any number of files in the DropTables folder, and they can be named anything you like as long as the file ends in .yml.

Drops
-----

Drops are the simplest way to implement custom drops.
```
internal_mobname:
  Type: <mobtype>
  Drops:
  - <item/exp/droptable> <amount> <chance>
  - <item/exp/droptable> <amount> <chance>
  - ...
```

**&lt;item/exp/droptable&gt;**  
Can be either an item from MythicMobs, a vanilla item, exp, a drop table or an item/experience for a supported plugin.

**&lt;amount&gt;**  
The amount of items to be dropped. Can be a number range; for example ```1-3```.

**&lt;chance&gt;**  
The chance for the specified item to be dropped.
  - Must be a number between 0 and 1 
  - **Note:** allows percentage chances. (10% instead of 0.1).

| **Special Drops**           | **Explanation**                                          | **Example**                             |
|-----------------------------|----------------------------------------------------------|-----------------------------------------|
| **champions-exp**           | Will drop experience points for the plugin *Champions*.  |                                         |
| **skillapi-exp**            | Will drop experience points for the plugin *SkillAPI*.   |                                         |
| **heroesexp**               | Will drop experience points for the plugin *Heroes*.     |                                         |
| **mcmmo-exp**               | Will drop experience points for the plugin *MCMMO*.      |                                         |
| **exp**                     | Will drop regular Minecraft experience points.           |                                         |
| **money**                   | Will drop money for the plugin *Vault*.                  |                                         |
| **mythicdrop &lt;item&gt;** | Will drop an &lt;item&gt; from the plugin *MythicDrops*. |                                         |
| **phatloot &lt;item&gt;**   | Will drop an &lt;item&gt; from the plugin *PhatLoot*.    |                                         |
| **cmd**                     | Will run a command in console                            | `- cmd{c="warp <trigger.name> spawn"}`  |
| **mmoitems**                | Drops a mmoitems item                                    | `- mmoitems{type=SWORD;id=CUTLASS} 1 1` |

[For more about MMOItems, see here.](https://git.lumine.io/mythiccraft/mmoitems/-/wikis/Item%20Drop%20Tables)

**In-line Drops**
------------------

For very basic equipment, you can add some inline item data so that you don't always have to create a mythic item. Options currently available in-line on builds below 4.12 include **name**, **data**, **amount**, **lore**, and **color**

All of this inline item data can also be used in [Equipment:](/mobs/equipment)!

```
 Drops:
 - leather_chestplate{name="Dark Leather";lore="&8A vest made of darkened leather";color=BLACK} 1 1
```

Options added in 4.12 are **model**, **enchants**, **potioneffects**, **skullOwner**, and **skulltexture**.

The below drops section will drop a Panda player head item that has 2 enchants on it, and will drop 3 pieces of diamond armor that all have names, lore, and enchantments on them!

```
  Drops:
  - PLAYER_HEAD{skullTexture=eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvYjY0NjNlNjRjZTI5NzY0ZGIzY2I0NjgwNmNlZTYwNmFmYzI0YmRmMGNlMTRiNjY2MGMyNzBhOTZjNzg3NDI2In19fQ==;enchants=WATER_WORKER:1,OXYGEN:3} 1 1
  - DIAMOND_CHESTPLATE{name="Panda<&sq>s Will";lore="A Panda must be vigilant";enchants=PROTECTION_ENVIRONMENTAL:4,DURABILITY:3,MENDING:1,THORNS:2} 1 1
  - DIAMOND_LEGGINGS{name="Panda<&sq>s Strength";lore="A Panda must be strong";enchants=PROTECTION_ENVIRONMENTAL:4,DURABILITY:3,MENDING:1,THORNS:2} 1 1
  - DIAMOND_BOOTS{name="Panda<&sq>s Speed";lore="A Panda must be fast";enchants=PROTECTION_ENVIRONMENTAL:4,DURABILITY:3,MENDING:1,PROTECTION_FALL:4,DEPTH_STRIDER:3} 1 1
```


Drop Tables
-----------

Drop Tables are collections of multiple drops that can be assigned to mobs. Using them makes it easier to organize your drops in almost any case where your mobs are supposed to drop multiple items.

Drop Tables are stored in their own respective configuration-files located in \/MythicMobs\/DropTables. They have the advantage of being able to utilize [Conditions](/Skills/Conditions) and various other special options, and can be shared by multiple mobs without the need of duplicating it.

Drop Tables can be nested - a Drop Table can contain multiple other Drop
Tables.
```
internal_mobname:
  Type: <mobtype>
  Drops:
  - <internal_droptablename>
```
The structure of a fully-configured drop table looks like this:
```
#Lets you specify exactly how many items will drop from this table
internal_droptablename: 
  TotalItems: <amount>
  MinItems: <amount> #defaults to TotalItems' value
  MaxItems: <amount> #defaults to TotalItems' value
  BonusLuckItems: <multiplier>
  BonusLevelItems: <multiplier>
#Conditions of the dropper
  Conditions:
  - condition 1
  - condition 2
  - ...
#Conditions of the person that triggered the drop (i.e. the killer of the mob)
  TriggerConditions:
  - condition 1
  - ...
  Drops:
  - <item/exp/droptable> <amount> <chance>
  - ...
```
DropTable Options
=================

**TotalItems: \[number\]**

-   Defines exactly how many items the table will drop
-   Setting this causes item chances to be calculated as weights

**MaxItems: \[number\]**

-   Defines a maximum number of items that will drop
-   If only this is set, drops will run down the list unless the maximum number of items is reached

**MinItems: \[number\]**

-   Defines a minimum number of items that will drop
-   If only this is set, drops will run down the list until the minimum items is reached
-   If you enable **both** ```MinItems``` and ```MaxItems```, the chances for each table entry will become *weights* instead.

**BonusLevelItems: \[number\]/\[range\]**

-   A modifier on the number of items dropped based on the mob's level
-   Can be set as a range,`i.e. ```0.2to0.5```
-   Works like:```amount = amount + (mob_level * bonus_level_items)```
-   Requires that```TotalItems```, ```MinItems```, or ```MaxItems``` are set on the table

**BonusLuckItems: \[number\]/\[range\]**

-   A modifier on the number of items dropped based on the killer's luck stat
-   Can be set as a range, i.e. ```0.15to8```
-   Works with Luck attribute, Luck-based enchants/curses, and Luck potion effects
-   Works like: ```amount = amount + (luck * bonus_luck\items)```
-   Requires that ```TotalItems```, ```MinItems```, or ```MaxItems``` are set on the table


Examples
--------

This mob will always drop a bunch of experience and some rotten flesh,
but is also using a droptable which is described further below.
```
snow_loving_zombie:
  Type: zombie
  Health: 100
  Equipment:
  - snowsword:0
  Drops:
  - exp 75-125 1
  - rare_snowsword_droptable
```

This example is a droptable that has a 5 % chance of dropping a custom
sword, but only if the mob is killed in an "ICE\_PLAINS" biome and if a
player is within 20 blocks.

```
rare_snowsword_droptable:
  Conditions:
  - inbiome ICE_PLAINS
  - playerwithin 20
  Drops:
  - snowsword 1 0.05
```
In this example, the DropTable would drop 5 gold/diamonds if the player
has no Luck, and 15-27 gold/diamonds if the player has a Luck V enchant.
```
LuckyDroptable:
  TotalItems: 5
  BonusLuckItems: 2to5
  Drops:
  - GOLD_NUGGET 1 1
  - DIAMOND 1 0.2
```