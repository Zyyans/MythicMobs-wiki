Mechanic: onShoot
=================

Applies an aura to the target that triggers a skill when they damage
something. Can use any aura attribute

Attributes
----------

| Attribute        | Aliases       | Description                                                | Default Value |
|------------------|---------------|------------------------------------------------------------|---------------|
| onHit            | oH            | Skill to execute if the target shoots something            |               |
| cancelEvent      | cE            | Whether or not to cancel the event that triggered the aura | false         |
| damageAdd        | add, a        |                                                            | 0             |
| damageMultiplier | multiplier, m |                                                            | 1             |

  

Examples
--------

      Skills:
      - onShoot{auraName=fireball_bow;onShoot=[ shootfireball ];duration=200;charges=5} @self
      - ...

In this example, the caster's next 5 bow shots will shoot fireballs
instead of arrows.
