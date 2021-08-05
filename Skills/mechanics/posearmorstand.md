Mechanic: PoseArmorStand
========================

Moves the extremities of an armorstand, the value is in radians.

Attributes
----------

| Attribute | Aliases | Description | Default Value |
|-----------|---------|-------------|---------------|
| head      |         |             | 0,0,0         |
| body      |         |             | 0,0,0         |
| leftarm   |         |             | 0,0,0         |
| rightarm  |         |             | 0,0,0         |
| leftleg   |         |             | 0,0,0         |
| rightleg  |         |             | 0,0,0         |

  

Examples
--------

      Skills:
      - posearmorstand{head=45,0,0} @self ~onSpawn
      - ...
