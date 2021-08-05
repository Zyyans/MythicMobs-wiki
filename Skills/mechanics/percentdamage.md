Mechanic: Damage Percent
========================

Deals damage equal to a percent of the player's max health, where 1 is
100%. Has the same options as the Damage mechanic.

Attributes
----------

| Attribute        | Aliases | Description                                                            | Default |
|------------------|---------|------------------------------------------------------------------------|---------|
| percent          | p       | The percentage to damage the target                                    | 0.1     |
| current          | c,ch    | Whether it calculates the percent from your original or current health | false   |
| ignoreArmor      | ia      | Whether or not to ignore armor                                         | false   |
| preventknockback | pkb, pk | Whether or not to prevent knockback                                    | false   |
| preventimmunity  | pi      | Whether or not to ignore immunities                                    | false   |

  

Examples
--------

      Skills:
      - damagepercent{percent=0.5}

Hurts the target for half (50%) of its max health.
