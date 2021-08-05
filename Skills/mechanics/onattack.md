Mechanic: onAttack
==================

Applies an aura to the target that triggers a skill when they damage
something. Can use any aura attribute

Attributes
----------

| Attribute        | Aliases       | Description                                                | Default Value |
|------------------|---------------|------------------------------------------------------------|---------------|
| onHit            | oH            | Skill to execute if the target hits something              |               |
| cancelEvent      | cE            | Whether or not to cancel the event that triggered the aura | false         |
| damageAdd        | add, a        |                                                            | 0             |
| damageMultiplier | multiplier, m |                                                            | 1             |

  

Examples
--------

      Skills:
      - onAttack{oH=SuperPunch;cE=true;auraname=MyAura}
      - ...
