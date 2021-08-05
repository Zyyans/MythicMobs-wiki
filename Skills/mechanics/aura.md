Mechanic: Aura
==============

The Aura mechanic acts as a status effect on the target entity, and can
trigger other skills over its duration. Auras allow you to create custom
status effects (i.e. buffs and debuffs) that are tracked for their
duration and can also be used in other mechanics and conditions.  

Attributes
----------

| Attribute           | Aliases | Description                                                                                                                                                                                 | Default Value |
|---------------------|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| auraName            |         | Optional name, required to use associated mechanics & conditions that reference a specific aura                                                                                             | None          |
| onStart             | oS      | Meta-Skill executed when the aura first starts.                                                                                                                                             | None          |
| onTick              | oT      | Meta-Skill executed every [interval] ticks on the affected entity.                                                                                                                        | None          |
| onEnd               | oE      | Meta-Skill executed when the aura fades.                                                                                                                                                    | None          |
| Charges             | c       | If set, the aura will fade when it hits zero charges. Modifiable by other mechanics.                                                                                                        | 0             |
| Duration            | d       | The max duration (in ticks) the aura will persist.                                                                                                                                          | 200           |
| Interval            | i       | How often (in ticks) the aura fires its onTick skill                                                                                                                                        | 1             |
| maxStacks           |         | How many times the aura stacks on the same targeted entity if applied multiple times (4.6.0 +)                                                                                              | None          |
| refreshDuration     |         | Makes the aura's duration refresh to the amount defined in the mechanic should the entity have the same aura applied to it again (4.6.0 +)                                                  | false         |
| mergeSameCaster     |         | Merges all of the same auras applied by one entity to another into one aura (Prevents a mob from being able to stack an aura multiple times on the same entity) (4.6.0 +)                   | false         |
| mergeAll            |         | Merges all of the same auras applied by any and all entities to another into one aura (Prevents multiple mobs from being able to stack an aura multiple times on the same entity) (4.6.0 +) | false         |
| CancelOnGiveDamage  | cogd    | Cancels the aura if the entity with the aura deals any damage to another entity.                                                                                                            | false         |
| CancelOnTakeDamage  | cotd    | Cancels the aura if entity with the aura takes any sort of damage.                                                                                                                          | false         |
| CancelOnDeath       | cod     | Cancels the aura if the entity with the aura dies.                                                                                                                                          | true          |
| CancelOnTeleport    | cot     | Cancels the aura if the entity with the aura teleports at all whether by another mechanic or server command.                                                                                | false         |
| CancelOnChangeWorld | cocw    | Cancels the aura if the entity with the aura changes worlds. (Most times applies to players)                                                                                                | false         |
| CancelOnSkillUse    | cosu    | Cancels the aura if the entity with the aura uses another skill while the aura is active.                                                                                                   | false         |
| CancelOnQuit        | coq     | Cancels the aura if the entity with the aura logs out. (Only really applies to players)                                                                                                     | true          |

  
===== Special Options (4.6.0 +)=====  
 The **onAttack** aura type has the following options:

-   All options available to Auras
-   **onHit=[skill]** - A skill to execute while the aura is active
-   **cancelEvent=true** - Whether to cancel the event and do no base
    damage
-   **multiplier=#** - An optional multiplier on the original hit's
    damage
-   **add=#** - An optional static increase to the original hit's
    damage

(See example below for usage)

The **onDamaged** aura type has the following options:

-   All options available to Auras
-   **onHit=[skill]** - A skill to execute while the aura is active
-   **cancelEvent=true** - Whether to cancel the event and damage taken
-   **multiplier=#** - An optional multiplier on the original hit's
    damage
-   **sub=#** - An optional static decrease (or increase if negative)
    to the original hit's damage

(See example below for usage)

Examples
--------

      Skills:
      - Aura{auraName=Retributing_Light;onTick=RetributingLightDamage;interval=10;duration=240} @self

Gives the target (Which in this case is the entity itself) the
Retributing_Light aura that lasts 12 seconds. Every 10 ticks (or half a
second) it will fire the RetributingLightDamage skill.

     Skills:
      - onDamaged{auraName=fire_shield;onHit=FireShield;duration=200;charges=5;multiplier=0.5} @self

In this example, the caster's next 5 hits taken in 10 seconds would
trigger the FireShield skill targeting whatever hit them and also deal
50% damage. However, if FireShield's conditions failed, it would deal
regular damage as the multiplier would not trigger either.

      Skills:
      - onAttack{auraName=fiery_strikes;onHit=FireStrike;duration=200;charges=5;multiplier=2} @self

In this example, the caster's next 5 physical hits within 10 seconds
would trigger the FireStrike skill targeting whatever was hit and also
deal 200% damage. However, if FireStrike's conditions failed, it would
deal regular damage as the multiplier would not trigger either.
