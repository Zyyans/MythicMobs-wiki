Mechanic: Set Block Type
========================

Change blocktype at target location.

Attributes
----------

| Attribute | Aliases | Description                    | Default Value |
|-----------|---------|--------------------------------|---------------|
| material  | m       | Any valid bukkit materialtype. | DIRT          |
| data      | md      | Material data value.           | 0             |

  

Examples
--------

    SetBlockExample:
      Skills:
      - setblock{m=STONE;md=0} @selflocation
