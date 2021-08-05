Mechanic: Shield
================

Adds absorption hearts. Having maxShield as a greater value than amount
is recommended.  
Doesn't work on **Minecraft below 1.13**(excluding 1.13).

Attributes
----------

| Attribute | Aliases           | Description | Default Value  |
|-----------|-------------------|-------------|----------------|
| amount    | a                 |             | 1              |
| maxabsorb | maxshield, ma, ms |             | Amount's value |

  

Examples
--------

      Skills:
      - shield{amount=50;maxShield=100} @self ~onSpawn
      - ...