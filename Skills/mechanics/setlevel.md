Mechanic: Set Level
===================

*Introduced in version 2.2.1*

Causes the casting mob to change it's level.

Possible operations for the action value are SET, ADD, SUBTRACT,
MULTIPLY, and DIVIDE.

Attributes
----------

| Attribute | Aliases | Description                            | Default Value |
|-----------|---------|----------------------------------------|---------------|
| action    | a       | Type of operation to perform           | SET           |
| level     | l       | Amount of levels used in the operation | 1             |

  

Examples
--------

This will set the mob level to 3 when it spawns

    - setlevel{a=set;l=3} ~onSpawn

This will increase the mob level by 1 each time it kills a player

    - setlevel{a=add;l=1} ~onKillPlayer
