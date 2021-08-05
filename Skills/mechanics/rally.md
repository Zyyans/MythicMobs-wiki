Mechanic: Rally
===============

Rallies all nearby mobs of the given types to focus-attack the given
target.

Attributes
----------

| Attribute       | Aliases | Description                                                                                        | Default Value |
|-----------------|---------|----------------------------------------------------------------------------------------------------|---------------|
| types           | type, t | A list of mob types to rally. The list can include both Mythic Mob types and regular Entity types. | NONE          |
| radius          | r       | The radius (in blocks) to rally mobs.                                                              | 10            |
| vradius         | vr      | Overrides the set vertical radius.                                                                 | radius        |
| hradius         | hr      | Overrides the set horizontal radius.                                                               | radius        |
| overwritetarget | ot      | (true/false) Whether to rally mobs that already have a target                                      | true          |

  

Examples
--------

This example would cause all mobs of the type "Guard" or "Knight" within
30 blocks, that don't already have a target, to attack the whatever or
whoever triggered this skill.

    CallForHelp:
      Skills:
      - message{m="<mob.name><&co> Guards! Help me!"} @PlayersInRadius{r=30}
      - rally{types=Guard,Knight;radius=30;ot=false} @Trigger
