Mechanic: Prison
================

Encases the target entity inside a temporary prison of blocks. The
created blocks will disappear automatically after the specified
duration.

Attributes
----------

| Attribute | Aliases | Description                                                  | Default Value |
|-----------|---------|--------------------------------------------------------------|---------------|
| material  | m       | The Material (block type) the prison is made out of.         | ICE           |
| duration  | d       | How long (in ticks) the prison will last                     | 100           |
| breakable | b       | (true/false) Whether or not the prison blocks can be broken. | false         |

  

Examples
--------

This skill creates a iron block prison around the target of the casting
mob, for 200 ticks (10 seconds), and the prison can be mined.

    IronPrison:
      Skills:
      - prison{material=IRON_BLOCK;duration=200;breakable=true} @target
