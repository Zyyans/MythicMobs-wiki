Enchantments
============

<img src="http://fs5.directupload.net/images/160308/2v6menmv.jpg" width="500" height="150" alt="http://fs5.directupload.net/images/160308/2v6menmv.jpg" />

The enchantments attribute is used to apply enchantments to items made using MythicMobs. Any of these can be put on any item and can exceed natural enchantment-level limits set by Minecraft. Some enchantments may not have any effects if put on items that they weren't made for.

Syntax
------
```
internal_itemname:
  Id: <item>
  Enchantments:
  - <enchantment>:<level>
  - <enchantment>:<level>
  - ...
```
**&lt;enchantment&gt;**  
Type of enchantment to be applied to the specified item.

**&lt;level&gt;**  
The level of the specified enchantment.
```
lethal_pickaxe:
  Id: diamond_pickaxe
  Enchantments:
  - DAMAGE_ALL:3
  - KNOCKBACK:1
```
Available Enchantments
----------------------

This is a list of all enchantments currently available in MythicMobs for
application on items.

[These use the Bukkit Enum for Enchantments, found here.](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/enchantments/Enchantment.html)

**ARROW\_DAMAGE**

-   "Power"
-   Used on bows.
-   Provides extra base damage when shooting arrows from bows.
-   Use this rather than "Damage: " option to increase damage for bows.

<img src="/databases/items/e_1.png" class="align-center" width="300" alt="databases/items/e_1.png" />

**ARROW\_FIRE**

-   "Flame"
-   Used on bows.
-   Sets target on fire.

**ARROW\_KNOCKBACK**

-   "Punch"
-   Used on bows.
-   Knock mob back further.
-   Can knockback mobs with 100% KnockbackResistance

**ARROW\_INFINITE**

-   "Infinity"
-   Used on bows.
-   Bow doesn't use arrows (need one arrow in inventory)
-   Same effect on all levels.

**DAMAGE\_ALL**

-   "Sharpness"
-   Used on melee weapons.
-   Increases damage with melee weapons to all mobs.
-   Adds 1.25 damage per level.

**DAMAGE\_ARTHROPODS**

-   "Bane of Arthropods"
-   Used on melee weapons.
-   Increases damage with melee weapons to spiders, cave spiders,
silverfish
-   Adds 2.5 damage per level.

**DAMAGE\_UNDEAD**

-   "Smite"
-   Used on melee weapons.
-   Increases damage with melee weapons to undead
-   Adds 2.5 damage per level.

**CHANNELING**

-   "Channeling"
-   Used on tridents.
-   If raining, strikes with lightning on impact with mob.
-   1 level max.

**SWEEPING\_EDGE**

-   "Sweeping Edge"
-   Used on swords.
-   Increases the damage from sword sweep attacks.
-   Higher damage per level.

**DIG\_SPEED**

-   "Efficiency"
-   Used on tools.
-   Increase dig speed by 30% over previous level.

**DURABILITY**

-   "Unbreaking"
-   Used on all items that have durability.
-   For most items (other than armor) lasts Level + 1 times as long
-   For armor, lasts 25%/36%/43% longer.

**MENDING**

-   "Mending"
-   Used on all items that have durability.
-   Repairs item using picked up XP.
-   2 durability per XP.

**FIRE\_ASPECT**

-   "Fire Aspect"
-   Used on melee weapons.
-   Adds 3 burn ticks per level to melee weapons.

**IMPALING**

-   "Impaling"
-   Used on melee weapons.
-   Deals extra damage to
[aquatic](https://minecraft.gamepedia.com/Mob#Underwater_Mobs) mobs
.
-   Does more damage per level.

**KNOCKBACK**

-   "Knockback"
-   Used on melee weapons.
-   Adds additional knockback to melee attacks. (Can knockback mobs with
100% KnockbackResistance)

**LOOT\_BONUS\_BLOCKS**

-   "Fortune"
-   Used on axes, shovels and pickaxes.
-   Increase chances of looting multiple rare blocks or rare items from
blocks.

**LOOT\_BONUS\_MOBS**

-   "Looting"
-   Used on melee weapons.
-   Increases maximum loot by 1 per level.
-   Increase chance for rare loot by 0.5% per level
-   At least 3 levels.

**LOYALTY**

-   "Loyalty"
-   Used on tridents.
-   Causes the trident to return when thrown.
-   At least 3 levels (uncertain what higher levels do).

**OXYGEN**

-   "Respiration"
-   Used on helmets.
-   Increase breathing time by 15 per level, decreases suffocation
damage and improves underwater vision
-   At least 3 levels

**PROTECTION\_ENVIRONMENTAL**

-   "Protection"
-   Used on armor.
-   Protects against all damage taken after normal armor is taken into
account.
-   At least 4 levels

**PROTECTION\_FALL**

-   "Feather Falling"
-   Used on boots.
-   Protects against fall damage taken after normal armor is taken into
account.
-   At least 4 levels

**PROTECTION\_FIRE**

-   "Fire Protection"
-   Used on armor.
-   Protects against fire damage taken after normal armor is taken into
account.
-   Reduces burn duration
-   At least 4 levels

**PROTECTION\_PROJECTILE**

-   "Projectile Protection"
-   Used on armor.
-   Protects against projectile damage taken after normal armor is taken
into account.
-   At least 4 levels

**PROTECTION\_EXPLOSIONS**

-   "Blast Protection"
-   Used on armor.
-   Protects against explosive damage taken after normal armor is taken
into account.
-   Reduces knockback from explosions.
-   At least 4 levels

**RIPTIDE**

-   "Riptide"
-   Used on tridents.
-   If raining or in water, launches player in direction of thrown
trident.
-   Higher levels increase speed.

**SILK\_TOUCH**

-   "Silk Touch"
-   Used on tools.
-   Allows player to obtain items which normally can't be obtained.
-   Same effect on all levels.

**THORNS**

-   "Thorns"
-   Used on armor.
-   ```Level X 15%``` chance of inflicting attacker for 1 to 4 damage.
-   Does not stack on multiple pieces.

**WATER\_WORKER**

-   "Aqua Affinity"
-   Used on helmets.
-   Allows player to break bricks underwater at regular speed.

**DEPTH\_STRIDER**

-   "Depth Strider"
-   Used on boots.
-   Allows player to move faster in water.

**FROST\_WALKER**

-   "Frost Walker"
-   Used on boots.
-   Freezes water under the players feet.
-   Increases radius with higher levels.

**BINDING\_CURSE**

-   "Curse of Binding"
-   Used on most items.
-   Items with curse can't be removed. (Except by dying)

**VANISHING\_CURSE**

-   *Curse of Vanishing*
-   Used on most items.
-   Items with curse vanish when player dies.

**MULTISHOT**

-   "Multishot"
-   Used on crossbows.
-   Fires 3 arrows as opposed to 1.
