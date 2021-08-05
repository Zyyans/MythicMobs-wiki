Mechanic: Force Pull
====================

Teleports all targeted entities to a location within &lt;spread&gt;
blocks of the casting mob.

Attributes
----------

| Attribute | Aliases | Description                                          | Default Value |
|-----------|---------|------------------------------------------------------|---------------|
| spread    | s       | How spread out players will be from the casting mob. | 0             |
| vspread   | vs      | Lets you override the vertical spread value          | spread        |

  

Examples
--------

This example would teleport all entities within 30 blocks to a random
location within 5 blocks of the boss.

    ForceGrip:
      Skills:
      - forcepull{spread=5} @EntitiesInRadius{r=30}
