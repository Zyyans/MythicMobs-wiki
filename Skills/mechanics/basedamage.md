Mechanic: BaseDamage
====================

*Added in version 2.3*

Damages the target entity for a percentage of the mob's damage stat.

Attributes
----------

| Attribute        | Aliases | Description                         | Default |
|------------------|---------|-------------------------------------|---------|
| multiplier       | m       | The percentage of damage to deal    | [1] 1   |
| ignoreArmor      | ia      | Whether or not to ignore armor      | false   |
| preventknockback | pkb, pk | Whether or not to prevent knockback | false   |
| preventimmunity  | pi      | Whether or not to ignore immunities | false   |

  

Examples
--------

This example will make the mob deal 150% of its original damage to its
target when its being attacked. In this case it would deal 15 damage,
since the mob's base-damage is 10.

      AMob:
        Type: HUSK
        Damage: 10
      Skills:
      - basedamage{m=1.5} @target ~onDamaged

[1] 1 = 100%, 0.5 = 50% and so-on
