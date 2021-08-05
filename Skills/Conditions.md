Introduction
------------

Conditions are used to determine whether or not an action may execute.
These conditions are placed under the Condition section in the
configuration as shown below (bottom of page).

Couldn't use [Variables](/skills/variables) in Condition's option

Conditions can be used in [1]:

-   [Skill Mechanics](/skills/mechanics/skill)
-   [Drop Tables](/Items/Drops#drop-tables)
-   [Spawners](/Spawners) (deprecated condition
    system)
-   [Random Spawners](/Random%20Spawns)

When applying multiple conditions, all of them must be met in order for
the action to be executed. Some conditions allow arrays that can be
split by commas. These conditions only require one of the strings in the
arrays to match.

To see how to use the premium only in-line target conditions, [click here!](/skills/conditions/in-linetargetconditions)

Usage
-----

### Types

  
Conditions can be broken into two types-

1.  General conditions: Those that can be used on entities and locations
    or on entities only.  
    - Compare conditions: Those that need two entities or two locations.
    This conditions only make sense if used in TargetConditions section
    in the skill yamls. **See CompareConditions!**  

Conditions that are used in the Conditions node of the skill:

-   Every condition can be used.
-   The caster is ALWAYS the entity that will be checked. All conditions
    can be used but conditions that compare 2 entities do not make sense
    here.

Conditions that are used in the TargetConditions node of the skill:

-   Every condition can be used.
-   TargetConditions node can only be used in skills.
-   The compare entity depends on the targeter of the skill. If the
    skill use @self the compare entity is the caster if the skill use
    any other targeter the compare entity/location is the entity given
    in the targeter.

### Examples

    Conditions:
    - globalscore{objective=Test;v=>10}

This condition is used under Conditions node and will always use the
caster as compare entity. No matter what the targeter of the skill is.

      TargetConditions:
      - globalscore{objective=Test;v=>10}

This (the same) condition is used under TargetConditions node and will
check the entity that is given by the targeter.

NOTE: CompareConditions only make sense in the TargetConditions node
because they compare 2 entities where 1 of them is always the caster and
the other one is the entitiy of the targeter. If they are used in the
Conditions node the caster and the target are always the same.

**Format**:  
Since 4.0.0, all conditions now have a new format.

    Conditions:
    - condition [variable]
    - condition [variable] [action]
    - condition [variable] [action] [action_variable]
    - condition{variable1=value;variable2=value} [action] [action_variable]

These new "actions" control how the skill acts when a condition is met
or not met. Here are some examples:

    Conditions:
    - day required
    - stance defensive power 0.5
    - stance{stance=defensive} power 0.5
    - score{objective=test;value=>20} cancel
    - haspotioneffect{type=POISON;level=>0;duration=0to100} true

**Ranged Values:**  
Ranged values use either the format **#to#** or **#-#**. You must
use "to" instead of "-" if you want to use negative numbers in the
range. Here for example the distance condition:

    TargetConditions:
    - distance{d=1to10} true

    TriggerConditions:
    - distance{d=1to10} true

    Conditions:
    - altitude{a=1-5}

Condition Actions
-----------------

Condition Actions allow you to do additional things based off of
conditions. The default condition action is **true**

| Action                     | Description                                                                |
|----------------------------|----------------------------------------------------------------------------|
| **required** (or **true**) | The condition is required for the skill to run.                            |
| **cancel** (or **false**)  | The skill will not run if this condition is met.                           |
| **power [multiplier]**   | Modifies the skill's power (e.i. power 2.0 would double the skill's power) |
| **cast [skill]**         | Casts an additional skill if the condition is met.                         |
| **castinstead [skill]**  | Casts a different skill instead if the condition is met.                   |
| **orElseCast [skill]**   | Casts a different skill instead if the condition is not met. (4.12 MM)     |

Conditions
----------

| Condition                                                    | Type     | Description                                                                                 |
|--------------------------------------------------------------|----------|---------------------------------------------------------------------------------------------|
| [Altitude](/conditions/altitude)                             | Entity   | Tests how far above the ground the target entity is                                         |
| [Biome](/conditions/biome)                                   | Location | Tests if the target is within the given list of biomes                                      |
| [BlockType](/conditions/blocktype)                           | Location | Tests the material type present at the target location                                      |
| [Blocking](/conditions/blocking)                             | Entity   | Tests if the target entity is blocking with a shield                                        |
| [Burning](/conditions/burning)                              | Entity | Whether or not the target entity is on fire |
| [Children](/conditions/children)                             | Entity   | Tests how many children the caster has                                                      |
| [Color](/conditions/color)                                   | Entity   | Tests the entity's colors |
| [Crouching](/conditions/crouching)                           | Entity   | Whether or not the target entity is crouching                                               |
| [Cuboid](/conditions/cuboid)                                 | Compare  | Whether the target is within the given cuboid between location1 x location2                 |
| [DamageAmount](/conditions/DamageAmount)                     | Entity   | Checks for a range of damage taken                                                          |
| [DamageCause](/conditions/DamageCause)                       | Entity   | Checks the type of the damage cause                                                          |
| [Dawn](/conditions/dawn)                                     | Location | If the time is dawn, from 22000 to 2000 in-game time                                        |
| [Day](/conditions/day)                                       | Location | If the time is day, from 2000 to 10000 in-game time                                         |
| [Distance](/conditions/distance)                             | Compare  | Whether the distance between the caster and target is within the given range                |
| [DistanceFromSpawn](/conditions/distancefromspawn)           | Location | Whether the distance from the world's spawn point to the target is within the given range   |
| [Dusk](/conditions/dusk)                                     | Location | If the time is dusk, from 14000 to 18000 in-game time.                                      |
| [EnchantingLevel](/conditions/enchantingLevel) | Entity | Checks the entity experience level |
| [EnderDragonPhase](/conditions/EnderDragonPhase)             | Entity   | Checks if the ender dragon is in a phase or phases                                           |
| [EntityType](/conditions/entitytype)                         | Entity   | Tests the entity type of the target                                                         |
| [Faction](/conditions/faction)                               | Entity   | Tests for the targets faction |
| [FallSpeed](/conditions/fallspeed)                           | Entity   | If the fall speed of the target is within the given range                                   |
| [FieldOfView](/conditions/fieldofview)                       | Compare  | Tests if the target is within the given angle from where the caster is looking              |
| [FoodLevel](/conditions/FoodLevel)                           | Entity   | Checks if the target has food within the range                                               |
| [FoodSaturation](/conditions/FoodSaturation)                 | Entity   | Checks if the target has food within the range                                               |
| [Gliding](/conditions/gliding)                               | Entity   | If the target is gliding                                                                    |
| [Globalscore](/conditions/globalscore)                       | Entity   | Checks a global scoreboard value                                                            |
| [HasAura](/conditions/hasaura)                               | Entity   | Checks if the target entity has the given aura                                              |
| [HasAuraStacks](/conditions/hasaurastacks)                   | Entity   | Tests if the target has the given range of stacks from an aura                              |
| [HasCurrency](/conditions/hascurrency)                       | Entity   | If the target has the given amount of vault currency                                        |
| [HasInventorySpace](/conditions/hasinventoryspace)           | Entity   | If the target has the given amount of empty inventory space                                 |
| [HasItem](/conditions/hasItem)                               | Entity   | Tests if the target player has the given number of given material                                                |
| [HasOwner](/conditions/hasowner)                             | Entity   | Tests if the target mob has an owner                                                        |
| [HasParent](/conditions/hasparent)                           | Entity   | Tests if the target mob has a parent                                                        |
| [HasPassenger](/skills/conditions/hasPassenger)              | Entity   | Checks if the target entity has a passenger                                                 |
| [HasGravity](/conditions/hasgravity)                         | Entity   | Tests if the target mob has gravity                                                         |
| [HasPotionEffect](/conditions/haspotioneffect)               | Entity   | Tests if the target entity has a potion effect                                              |
| [HasTag](/conditions/hastag)                                 | Entity   | Tests if the target has a scoreboard tag                                                    |
| [Haspermission](/conditions/haspermission)                   | Entity   | Tests if the target player has a permission                                                 |
| [Health](/conditions/health)                                 | Entity   | Matches the target's health                                                                 |
| [Height](/conditions/height)                                 | Location | Checks if the target's Y location is within a range                                         |
| [HeightAbove](/conditions/heightabove)                       | Location | Checks if the target's Y location is above a value                                          |
| [HeightBelow](/conditions/heightbelow)                       | Location | Checks if the target's Y location is below a given value                                    |
| [Holding](/conditions/holding)                               | Entity   | Checks if the target is holding a given material(support MythicMobs and MMOItems)                                            |
| [Inblock](/conditions/inblock)                               | Location | Checks the material at the target location                                                  |
| [Incombat](/conditions/incombat)                             | Entity   | If the target mob is considered in combat                                                   |
| [Inside](/conditions/inside)                                 | Location | Checks if the target has a block over their head                                            |
| [isCaster](/skills/conditions/iscaster)                      | Entity   | Checks if the target is the caster                                                         |
| [isChild](/skills/conditions/ischild)                        | Entity   | Checks if the target is a child of the caster                                            |
| [isLiving](/skills/conditions/isliving)                      | Entity   | Checks if the target is a living entity                                                  |
| [isMonster](/skills/conditions/ismonster)                      | Entity   | Checks if the target is a monster                                                         |
| [isPlayer](/skills/conditions/isplayer)                      | Entity   | Checks if the target is a player                                                         |
| [isSprinting](/skills/conditions/issprinting)                | Entity   | Checks if the target **Player** is sprinting                                        |
| [ItemRecharging](/conditions/itemrecharging)                 | Entity   | Checks if the target's weapon is recharging                                                 |
| [LastDamageCause](/conditions/lastdamagecause)               | Entity   | Checks the target's last damage cause                                                       |
| [LastSignal](/conditions/lastsignal)                         | Entity   | Matches the last signal received by the target mob                                          |
| [Level](/conditions/level)                                   | Entity   | Checks the target MythicMob's level                                                         |
| [LightLevel](/conditions/lightlevel)                         | Location | Tests the light level at the target location                                                |
| [LineOfSight](/conditions/lineofsight)                       | Compare  | Tests if the target is within line of sight of the caster                                   |
| [LunarPhase](/conditions/lunarphase)                         | Location | Checks the target world's lunar phase                                                       |
| [Mobsinradius](/conditions/mobsinradius)                     | Location | Checks how many mobs are in a given radius                                                  |
| [Mobsinchunk](/conditions/mobsinchunk)                       | Location | Matches a range to how many mobs are in the target location's chunk                         |
| [Mobsinworld](/conditions/mobsinworld)                       | Location | Matches a range to how many mobs are in the target world                                    |
| [Mounted](/conditions/mounted)                               | Entity   | If the target entity is riding a mount/vehicle                                              |
| [Moving](/conditions/moving)                                 | Entity   | If the target has a velocity greater than zero                                              |
| [MythicMobType](/conditions/mythicmobtype)                   | Entity   | Checks the MythicMob type of the target mob                                                 |
| [Night](/conditions/night)                                   | Location | If the time is night, from 14000 to 22000 in-game time                                      |
| [NotInRegion](/conditions/notinregion)                       | Location | If the target location is not within the given WorldGuard region                            |
| [OffGCD](/conditions/offgcd)                                 | Entity   | Checks if the target mob has an active Global Cooldown                                      |
| [OnBlock](/conditions/onblock)                               | Location | Matches the block the target entity is standing on                                          |
| [OnGround](/conditions/onground)                             | Entity   | If the target entity is standing on solid ground                                            |
| [Outside](/conditions/outside)                               | Location | If the target has open sky above them                                                       |
| [Owner](/conditions/owner)                                   | Compare  | Checks if the target entity is the owner of the caster                                      |
| [OwnerIsOnline](/conditions/ownerisonline)                   | Entity   | Checks if the owner of the target mob is online, if the owner is a player                   |
| [Pitch](/conditions/pitch)                                   | Entity   | Checks if the pitch of the target entity is within a range                                  |
| [PlayerKills](/conditions/playerkills)                       | Entity   | Matches how many players the target mob has killed                                          |
| [PlayersInRadius](/conditions/playersinradius)               | Entity   | Checks how many players are in a radius                                                       |
| [PlayerNotWithin](/conditions/playernotwithin)               | Location | Checks if any players are within a radius of the target                                     |
| [PlayerWithin](/conditions/playerwithin)                     | Location | Checks if any players are within a radius of the target                                     |
| [Raining](/conditions/raining)                               | Location | If it's raining in the target world                                                         |
| [Region](/conditions/region)                                 | Location | If the target is within the given WorldGuard region                                         |
| [SameFaction](/conditions/samefaction)                       | Entity   | Tests if the caster and target are in the same faction                                      |
| [Score](/conditions/score)                                   | Entity   | Checks a scoreboard value of the target entity                                              |
| [SlimeSize](/skills/conditions/slimesize)                    | Entity   | Checks the size of the target entity                                                         |
| [Stance](/conditions/stance)                                 | Entity   | Checks the stance of the target mob                                                         |
| [StringEquals](/conditions/stringequals)                     | Meta     | Checks if value1 equals value2. Both values can use variables and placeholders.             |
| [Sunny](/conditions/sunny)                                   | Location | If the weather is sunny in the target world.                                                |
| [TargetInLineOfSight](/conditions/targetinlineofsight)       | Entity   | Tests if the target has line of sight to their target                                       |
| [TargetNotInLineOfSight](/conditions/targetnotinlineofsight) | Entity   | Tests if the target doesn't have line of sight to their target                              |
| [TargetWithin](/conditions/targetwithin)                     | Entity   | Tests if the target's target is within a certain distance                                   |
| [Targetnotwithin](/conditions/targetnotwithin)               | Entity   | Tests if the target's target is not within a certain distance                               |
| [Targets](/conditions/targets)                               | Meta     | Tests if the number of inherited targets from the parent skilltree matches the given range. |
| [Thundering](/conditions/thundering)                         | Location | If it's thundering in the target world                                                      |
| [VariableInRange](/conditions/variableinrange)               | Meta     | Checks if the given numeric variable is within a certain range.                             |
| [VariableIsSet](/conditions/variableisset)                   | Meta     | Checks if the given variable is set.                                                        |
| [Variableequals](/conditions/variableequals)                 | Meta     | Checks if the given variable has a particular value.                                        |
| [Wearing](/conditions/wearing)                               | Entity   | Tests what the target entity has equipped.                                                  |
| [World](/conditions/world)                                   | Location | Checks the name of the target world.                                                        |
| [Worldtime](/conditions/worldtime)                           | Location | Matches a range against the target location's world's time.                                 |
| [Yaw](/conditions/yaw)                                       | Entity   | Checks the yaw of the target entity against a range.                                        |
| [yDiff](/conditions/ydiff)                                       | Entity   | Checks the difference in Y between the targeted entity and the caster.                                        |

More Examples
-------------

    FlameShock:
      Cooldown: 1
      Conditions:
      - targetwithin 15
      - targetinlineofsight true
      - incombat
      - stance aggressive
      - onblock GRASS
      - offgcd
      Skills:
      - gcd{t=60}
      - message{m="<mob.name> begins casting a spell"}
      - potion{t=SLOW;d=60;l=7}
      - delay 60
      - message{m="<target.name> &ecombusts"}
      - effect:particles{p=flame;a=20;hS=3;vS=1;s=0;y=2}
      - potion{t=HARM;d=1;l=1}

[1] Not all conditions may be applicable everywhere.