Mechanic: Lightning
===================

Causes a lightning strike at the target entity or location, dealing
damage and potentially setting the target entity or block on fire if it
is not currently raining, but only if fire spread is enabled.

Attributes
----------

| Attribute | Aliases | Description                                | Default Value |
|-----------|---------|--------------------------------------------|---------------|
| damage    | d       | The amount of damage the strike will deal. | 0.01337       |

  

Examples
--------

This example will summon a lightning bolt to the designated targeters.

    StaticSheep:
      Type: SHEEP
      Skills:
      - lightning @EntitiesInRadius{r=10} ~onTimer:100

This example will summon a lightning bolt to the designated targeters and deal 6 damage.

    StaticSheep:
      Type: SHEEP
      Skills:
      - lightning{d=6} @EntitiesInRadius{r=10} ~onTimer:100
