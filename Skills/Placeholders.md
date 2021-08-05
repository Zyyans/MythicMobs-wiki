# Placeholders
------------

These are all of the placeholders and special characters you can use in
skills and mechanics that use strings. There are some examples of usage at the bottom to get you started.

__**Note:** Usage of many variables in skills are locked to the premium versions, excluding MMOCore, special characters, color codes, and `setvariable`__.

Special Characters
------------------

| **Placeholder** | **Function**                          |
|-----------------|---------------------------------------|
| <&co>     | Returns a colon (:)                   |
| <&sq>     | Returns an apostrophe (')             |
| <&da>     | Returns a dash (-)                    |
| <&bs>     | Returns a backslash (\\)              |
| <&fs>     | Returns a forward slash (/)           |
| <&sp>     | Returns a space                       |
| <&cm>     | Returns a comma (,)                   |
| <&sc>     | Returns a semicolon (;)               |
| <&eq>     | Returns an equals symbol \[=\]        |
| <&ss>     | Returns a section symbol (ยง)         |
| <&dq>     | Returns double quotes (")             |
| <&rb>     | Returns a right bracket (\])          |
| <&lb>     | Returns a left bracket (\[)           |
| <&rc>     | Returns a right curly bracket (})     |
| <&lc>     | Returns a left curly bracket ({)      |
| <&nl>     | Forces a new line                     |
| <&heart>  | Returns a heart                       |
| <&skull>  | Returns a skull and bones             |

Color Codes
-----------

These color codes work anywhere in mob- and skill-files. They will even
properly format tellraw-commands used in command skills!

| **Code** | **Color**   | **Code** | **Color**      |
|----------|-------------|----------|----------------|
| &0       | Black       | &B       | Aqua           |
| &1       | Dark Blue   | &C       | Red            |
| &2       | Dark Green  | &D       | Light Purple   |
| &3       | Dark Aqua   | &E       | Yellow         |
| &4       | Dark Red    | &F       | White          |
| &5       | Dark Purple | &K       | Magic          |
| &6       | Gold        | &L       | Bold           |
| &7       | Gray        | &M       | Strike through |
| &8       | Dark Gray   | N       | Underline      |
| &9       | Blue        | &O       | Italic         |
| &A       | Green       | &R       | Reset          |

Caster Placeholders
------------------
These placeholders will return whatever attribute of the caster that is called. For instance `<caster.l.y.#>` will return the caster's Y location.

|Caster Placeholder|Function|
|----------------------------------|-------------------------------------------------------------------------|
|<caster.damage>|Returns the total amount of taken damage|
|<caster.uuid>|Returns the UUID of the caster|
|<caster.level>|Returns the level of the caster|
|<caster.name>|Returns the name of the caster|
|<caster.hp>|Returns current hp of the caster|
|<caster.mhp>|Returns the max hp of the caster|
|<caster.php>|Returns the percent hp of the caster|
|<caster.thp>|Returns the full number hp of the caster|
|<caster.tt.top>|Returns the name of the top threat holder of the caster|
|<caster.l.w>|Returns the world name the caster is in|
|<caster.l.x>|Returns the X coordinate of the caster|
|<caster.l.x.#>|Returns the X coordinate of the caster +- random number between #|
|<caster.l.x.double>|Returns the precise X coordinate of the caster|
|<caster.l.y>|Returns the Y coordinate of the caster|
|<caster.l.y.#>|Returns the Y coordinate of the caster +- random number between #|
|<caster.l.y.double>|Returns the precise Y coordinate of the caster|
|<caster.l.z>|Returns the Z coordinate of the caster|
|<caster.l.z.#>|Returns the Z coordinate of the caster +- random number between #|
|<caster.l.z.double>|Returns the precise Z coordinate of the caster|
|<caster.l.yaw>|Returns the yaw of the caster|
|<caster.l.pitch>|Returns the pitch of the caster|
|<caster.stance>|Returns the current stance of the caster|
|<caster.owner.name>|Returns the name of the wolf's owner|
|<caster.owner.uuid>|Returns the uuid of the wolf's owner|


**Variable Placeholders**
-----------------
These placeholders will return whatever variable has been called. For instance <caster.var.\[name\]> will return the value of the caster's \[name\] variable.

| **Variable Placeholder** | **Function** |     
|----------------------------------|-------------------------------------------------------------------------|
| <caster.var.\[name\]>      | Returns the value of the variable \[name\] on the caster. |
| <skill.var.\[name\]>       | Returns the value of the variable \[name\] on the current skill tree.|
| <skill.var.damage-amount>  | Returns the amount of damage taken in the onDamaged trigger |
| <skill.var.damage-type>    | Returns the type of damage taken as specified in a mechanic, aura, etc.|
| <skill.var.aura-name>      | Returns the name of the aura as specified in an aura. |
| <skill.var.aura-charges>   | Returns the amount of charges the aura has left.      |
| <skill.var.aura-duration>  | Returns the duration of the aura.                     |
| <skill.var.aura-stacks>    | Returns the amount of stacks the aura has.            |
| <skill.targets>            | Returns skill's targeted entities                     |
**Target Placeholders**
-----------------
These placeholders will return whatever target selector has been used. For instance <target.name> + @NearestPlayer will return the name of the player closest to the casting mob.

| **Target Placeholders** | **Function**   |
|----------------------------------|-------------------------------------------------------------------------|
|<target.uuid>|Returns the UUID of the target|
|<target.name>|Returns the name of the target|
|<target.hp>|Returns the current hp of the target|
|<target.threat>|Returns the threat level of the target|
|<target.l.w>|Returns the world name the target is in|
|<target.l.x>|Returns the X coordinate of the target|
|<target.l.x.#>|Returns the X coordinate of the target +- random number between #|
|<target.l.y>|Returns the Y coordinate of the target|
|<target.l.y.#>|Returns the Y coordinate of the target +- random number between #|
|<target.l.z>|Returns the Z coordinate of the target|
|<target.l.z.#>|Returns the Z coordinate of the target +- random number between #|
|<target.l.yaw>   |Returns the yaw of the target|
|<target.l.pitch> |Returns the pitch of the target|
|<target.level> |Returns the level of the target|
|<target.block.type> |Returns the block type of the target|
|<target.entity.type> |Returns the entity type of the target|

**Trigger Placeholders**
These placeholders will return whatever attribute of the entity that caused the skill to happen. For instance `<trigger.name>` combined with an `~onDeath` trigger will return the name of the entity that killed the mob.

    Skills:
    - message{m="<&b><caster.name><&r> was slain by <&a><trigger.name><&r>."} @PIR{r=20} ~onDeath

-----------------
|Trigger Placeholders|Function|
|------------------|--------------------------------------------------------------------------------------|
|<trigger.uuid>    |Returns the UUID of the entity triggering the skill|
|<trigger.name>    |Returns the name of the entity triggering the skill|
|<trigger.hp>      |Returns the current hp of the entity triggering the skill|
|<trigger.threat>  |Returns the threat level of the entity triggering the skill|
|<trigger.l.w>     |Returns the world name of the entity triggering the skill|
|<trigger.l.x>     |Returns the X coordinate of the entity triggering the skill|
|<trigger.l.x.#>   |Returns the X coordinate of the entity triggering the skill +- random number between #|
|<trigger.l.y>     |Returns the Y coordinate of the entity triggering the skill|
|<trigger.l.y.#>   |Returns the Y coordinate of the entity triggering the skill +- random number between #|
|<trigger.l.z>     |Returns the Z coordinate of the entity triggering the skill|
|<trigger.l.z.#>   |Returns the Z coordinate of the entity triggering the skill +- random number between #|
|<trigger.l.yaw>   |Returns the yaw of the trigger|
|<trigger.l.pitch> |Returns the pitch of the trigger|
  

Misc Placeholders
-----------------

| **Placeholder**       | **Function**                                        |
|-----------------------|-----------------------------------------------------|
| **Misc Placeholders** |                                                     |
| <drops.xp>      | Returns the xp dropped via Heroes or SkillAPI mods  |
| <drops.money>   | Returns the money dropped through the vault plug-in |

Special Placeholders
--------------------

| **Placeholder**                        | **Function**                                                              |
|----------------------------------------|---------------------------------------------------------------------------|
| <caster.score.objective>         | Returns the score of the caster from "objective" **(2.3)**                |
| <target.score.objective>         | Returns the targeters score from "objective" **(2.3)**                    |
| <trigger.score.objective>        | Returns the score of the trigger from "objective" **(2.3)**               |
| <global.score.objective>         | Returns the global score from "objective" **(2.3)**                       |
| <score.objective.dummyname>      | Returns the score of "dummyname" (fake player) from "objective" **(2.3)** |
| <random.\#-\#>  | Returns a random number in the specified range                                             |

Examples
--------------------

**This will make a mob send a teal message to all players in a radius of 20 blocks around in itself, stating what entity killed it in green.**

```
    Skills:
    - message{m="<&b><caster.name><&r> was slain by <&a><trigger.name><&r>."} @PIR{r=20} ~onDeath
```

**This skill will make an announcement when the mob spawns that looks like this:**

![image](uploads/91ed6d8aaa669e8ae21f8745e8ff4643/image.png)

```
  Skills:
  - Skill{s=SaveBossLocation} @self ~onSpawn
  - message{m="&eA &BGiant Zombie&e (Level &4<caster.level>&e) &ehas spawned at <caster.var.SpawnLoc>"} ~onSpawn @PlayersInWorld
  - message{m="&eThe &BGiant Zombie&e (Level &4<caster.level>&e) &espawned at <caster.var.SpawnLoc>&e has been slain."} ~onDeath @PlayersInWorld
```

Be sure to place this skill somewhere in the skills file

```
SaveBossLocation:
  Skills:
  - setvariable{var=SpawnLoc;type=STRING;value="&b<caster.l.x>&e, &b<caster.l.y>&e, &b<caster.l.z>";scope=CASTER} @self
```
**You can also use color tags and formatting tags to make the mobs have pretty names:**

![image](uploads/9ad97422803c3f35fbeac2e4df7f7d52/image.png)

```
ZOMBIE:
  Display: 'ZOMBIE &F- &A<caster.hp>/<caster.mhp>HP &F- &ELv.<caster.level>'
```