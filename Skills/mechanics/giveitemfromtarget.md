Mechanic: Give Item From Target
===============================

Gives the caster an item while playing the pickup-item animation from the target entity or location when fakelooting is set to true.

Gives the caster an item from the target entity or location when fakelooting is set to false.

Attributes
----------

| Attribute   | Aliases | Description       | Default Value |
|-------------|---------|-------------------|---------------|
| item        | i       | The item material |               |
| amount      | a       | The amount given  | 1             |
| fakeLooting |         | plays the pickup-item animation from the target | false |

------------

This mechanic was added in 4.12 MM

Examples
--------

    Skills:
    - giveitem{i=diamond_sword;a=1} @PIR{r=20} ~onSpawn
    - ...
