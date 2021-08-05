Mechanic: HealPercent
=====================

*Added in version 2.3*

Heals the target entity for a percentage of its max-health. Like the
heal skill, can also overheal mobs by a percentage.

Attributes
----------

| Attribute  | Aliases | Description                                                 | Default |
|------------|---------|-------------------------------------------------------------|---------|
| multiplier | m       | The percentage to heal, refers to the targets max-health    | [1] 0.1 |
| overheal   |         | Whether or not to apply overhealing as additional MaxHealth | false   |

  

Examples
--------

This will make the casting mob heal for 20% of its health each time it
gets to attack.

      Skills:
      - healpercent{m=0.2} @self ~onAttack

[1] 1 = 100 %, 0.5 = 50 % and so on...
