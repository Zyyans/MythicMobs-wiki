Mechanic: Stun
==============

Holds the target in place temporarily.

Attributes
----------

| Attribute           | Aliases | Description                                                                                                  | Default Value |
|---------------------|---------|--------------------------------------------------------------------------------------------------------------|---------------|
| duration            | d       | The duration (in ticks) the stun will last                                                                   |               |
| stopai              | ai      | Removes entity AI while stunned                                                                              | false         |
| gravity             | g       | Remove gravity from target when stunned (1.9+)                                                               | false         |
| facing              | face, f | When false, entity cannot rotate or look around when stunned                                                 | false         |
| CancelOnGiveDamage  | cogd    | Cancels the stun if the entity with the stun deals any damage to another entity.                             | false         |
| CancelOnTakeDamage  | cotd    | Cancels the stun if entity with the stun takes any sort of damage.                                           | false         |
| CancelOnDeath       | cod     | Cancels the stun if the entity with the stun dies.                                                           | true          |
| CancelOnTeleport    | cot     | Cancels the stun if the entity with the stun teleports at all whether by another mechanic or server command. | false         |
| CancelOnChangeWorld | cocw    | Cancels the stun if the entity with the stun changes worlds. (Most times applies to players)                 | false         |
| CancelOnSkillUse    | cosu    | Cancels the stun if the entity that is stunned uses another skill while the stun is active.                  | false         |
| CancelOnQuit        | coq     | Cancels the stun if the entity with the stun logs out. (Only really applies to players)                      | true          |

  

Special Notes
-------------

This mechanic can cause Spigot to kick the player (PlayerName moved
wrongly!)

Examples
--------

Stuns the target for 3 seconds, target can rotate.

    Freeze:
      Skills:
      - stun{d=60;f=true} @target
