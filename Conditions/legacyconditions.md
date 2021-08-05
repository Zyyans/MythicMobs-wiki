**Legacy Conditions**
=====================

This is the conditions page for MythicMobs 2.5.11 and below. You can still use this in MythicMobs 4.0.0+ by specifying “LegacyConditions” instead of just Conditions.

Conditions are used to determine whether or not an action may execute. These conditions are placed under the Condition section in the configuration as shown below (bottom of page).

Conditions can be used on
- [Skill Mechanics](/skills/mechanics/skill)
- [DropTables](/Items/Drops#drop-tables)
- [Spawners](/Spawners)
- [Random Spawns](/Random%20Spawns)

When applying multiple conditions, all of them must be met in order for the action to be executed. Some conditions allow arrays that can be split by commata. These conditions only require one of the strings in the arrays to match.

**Conditions**
-------------------
| Conditions | Description |
|------------|-------------|
| biome [biomename] | Execute the skill if the mob is in a particular [biome](https://github.com/Bukkit/mc-dev/blob/master/net/minecraft/server/BiomeBase.java). `biome FOREST` |
| distancefromspawnp[number] | Test for the distance from the world spawn point. Can be number ranges (10-405), single numbers or >10, <77 etc. `distancefromspawn >100` |
| globalscore [objective];[score] | tests for the score of the player \_GLOBAL\_. `globalscore playerkills;>10` |
| height [number_range] | Execute the skill if the mob is within a particular height range. Can be a single number, a range (20-40), or >10 <5, etc. Pressing F3 will show you your height for reference. `height 0-20` |
| heightabove / heightbelow [number] | Execute the skill if the mob is above or below a particular height. Pressing F3 will show you your height for reference. `heightabove 0` |
| holding [itemname] | Executes the skill if the casting mob is holding [itemname]. Must be a bukkit [material name](https://github.com/Bukkit/Bukkit/blob/master/src/main/java/org/bukkit/Material.java). Can't be a mythic item. Due to a mysterious bug this condition can't test for items with durability (as of 2.2.1 and before). `holding STICK` |
| inblock [material_type] | Execute the skill if the mob is in a particular [block material](https://github.com/Bukkit/Bukkit/blob/master/src/main/java/org/bukkit/Material.java). Useful generally to check if a mob is in water, air, lava, etc rather than a solid material. Allows arrays/data splits. Note that for mobs inside water blocks, you want STATIONARY_WATER instead of just WATER. `inblock WATER` |
| incombat | Execute the skill if the mob is currently in combat (mob has a target). `incombat` |
| inregion/notinregion [region] | Execute the skill if the mob is in a particular region defined by WorldGuard plugin. `inregion castle` |
| lastsignal [signal] (2.2.1) | Execute the skill if the last signal received matches [signal] - see [signal skill](/Skills/mechanics/signal). Unlike the stance condition, the lastsignal condition checks for perfectly matching data. `lastsignal ping` |
| level [number_range] | Execute the skill if the mob is of a particular level range. Can be a single number, a range (20-40), or >10, <5, etc. `level >3` |
| lightlevel [number_range] | Execute the skill if the mob in a light level within a certain range. Must be a number between 0 and 15. `lightlevel 0-3` |
| lightlevelabove / lightlevelbelow [number] | Execute the skill if the mob is located in a light level above or below a certain number. `lightlevelabove 6` |
| lunarphase [phase] | Execute the skill if it is a particular day. Comma separated list of game days (0*7) representing the lunar phase. `lunarphase 0,2,4` |
| mobscore [objective];[score] (2.3) | tests for the score of the casting mob. `mobscore timestuff;=3` |
| mobsinchunk [number_range] | Execute the skill if a certain amount of mobs are present in the chunk. Can be a single number, a range (20-40), or >10, <5, etc. `mobsinchunk <20` |
| mobsinworld [number_range] | Execute the skill if a certain amount of mobs are present in the world. Can be a single number, a range (20-40), or >10 <5, etc. `mobsinworld >100` |
| mobtype [mobname] | Spawn the mob if the mob matches [mobname]. Only works in random spawn files. Allows arrays/data splits. `mobtype COW` |
| offgcd | Executes the skill if the mobs global cooldown is 0. The mobs global cooldown is a time period or delay during which the mob can not execute any skills (if defined as such using this condition). Must use the GCD skill to set the global cooldown in a skill or the global cooldown will always be 0. Frequently used for mobs that have more than one spell or skill to keep them from casting them simultaneously which generally is not preferred. `offgcd` |
| onblock [material_type] | Execute the skill if the mob is standing on a particular block [material](https://github.com/Bukkit/Bukkit/blob/master/src/main/java/org/bukkit/Material.java). Allows arrays/data splits. `onblock grass` |
| outside/inside [true/false] | Execute the skill if the mob is either inside or outside. Outside is defined by the mob having a clear line of sight to the sky. Inside is the opposite. `outside true` |
| playerkills [number] | Execute the skill if the mob's playerkill-count matches [number]. `playerkills 7` |
| playernotwithin/targetnotwithin [distance] | Execute the skill if the player is not within a certain amount of blocks. Accepts a single number. If you wish to use a range, use targetdistance condition instead. `playernotwithin 5` `targetnotwithin 2` |
| playerwithin/targetwithin [distance] | Execute the skill if the player is within a certain amount of blocks. Accepts a single number. If you wish to use a range, use targetdistance condition instead. Frequently used along with targetinlineofsight condition to keep mobs from using skills on players that they can't see or are too far away. `playerwithin 15` `targetwithin 7` |
| raining [true/false] | Executes the skill if it is raining or not. `raining false` |
| score (2.3) | Tests for the score of fake players
`score <objective>;<entry>;<numberrange>`. `score kills;dummyplayer;10-14` |
| stance [string] | Executes the skill if the mob is in a particular stance. Stance variable must be defined previously using the setstance skill and can be any string that makes sense to the player for the skill being designed. The stance condition will check for the given string being contained in the current stance. This allows complex useage of the condition. For instance if your mob's stance is AGGRO and your stance condition only checks for GG the stance will match. `stance defensive` |
| sunny [true/false] | Executes the skill if it is sunny or not. `sunny true` |
| targetscore [objective];[score] (2.3) | Tests for the score of the casting mob's target. `targetscore mobkills;>99` |
| targetdistance [number_range] | Executes the skill if the mob is within specific distance range. Accepts a range (10-20, etc). Slightly more CPU intensive then targetwith / targetnotwithin so use those if you don't require a particular range. `targetdistance 10-20` |
| targetinlineofsight / targetnotinlineofsight [true/false] | Executes the skill if the mob has or does not have line of sight to the player. Frequently used with targetwithin / targetnotwithin conditions for detrimental type skills. `targetinlineofsight true` |
| thundering [true/false] | Executes a skill if it is thundering or not. `thundering false` |
| world [worldname] | Executes a skill if in a particular world. Can be single world or a comma separated list. Allows arrays/data splits. `world snowyworld, lavaworld, islandworld` |
| worldtime [number_range] | Executes a skill if during a particular time of day. Valid values are between 0 and 24000. (`/time` will tell you the time of day in ticks) 0-12000 is the minecraft day. 12001-13800 is dusk, 13801-22200 is night, 22201-24000 is dawn. `worldtime 0-12000` |

**Examples**
------------
```yaml
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
```