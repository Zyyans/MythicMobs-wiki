Mechanic: GlobalCooldown
========================

The "GCD" or "Global Cooldown" skill lets you set a mob's global
cooldown, used in conjunction with the "offgcd" condition if you want a
mob's abilities to have a global, over-all shared cooldown.

Attributes
----------

| Attribute | Aliases | Description                   | Default Value |
|-----------|---------|-------------------------------|---------------|
| ticks     | t       | How many ticks to set the GCD | 20            |

  

Examples
--------

This skill would trigger a Global Cooldown of 40 ticks, during which the
skill and all other skills using the "offgcd" condition would not be
usable.

      IceBolt:
        Conditions:
        - offgcd
        - targetinlineofsight
        Skills:
        - gcd{ticks=40}
