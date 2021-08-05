Mechanic: Consume
=================

Damages each entity targeted for the given amount, and heals the casting
mob for each entity that takes damage this way.

Attributes
----------

| Attribute        | Aliases | Description                           | Default |
|------------------|---------|---------------------------------------|---------|
| damage           | d,dmg   | The amount of damage to deal          | None    |
| heal             | h       | The amount of healing per mob damaged | None    |
| preventknockback | pkb, pk | Whether or not to prevent knockback   | false   |
| preventimmunity  | pi      | Whether or not to ignore immunities   | false   |
| ignorearmor      | i,ia    | Whether or not to ignore target armor | false   |

*"preventknockback" and "preventimmunity" were added in version 2.3*  

Examples
--------

Would consume all nearby zombies, healing the boss for 20 hp for each
zombie killed.

      Skills:
      - consume{d=1000;h=20} @MobsInRadius{type=ZOMBIE;r=20}
