Mechanic: ShieldPercent
=======================

Applies an absorb shield to the target entity for a percentage of their
max health.  
Doesn't work on **Minecraft below 1.13**(excluding 1.13).

Attributes
----------

| Attribute  | Aliases           | Description | Default Value      |
|------------|-------------------|-------------|--------------------|
| multiplier | m                 |             | 0.1                |
| maxabsorb  | maxshield, ma, ms |             | Multiplier's value |

  

Examples
--------

      Skills:
      - shieldPercent{multiplier=2;mS=2.5} @self ~onTimer:2000
      - ...