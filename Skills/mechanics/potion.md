Mechanic: Potion
================

Applies a potion effect to the target entity, which is usually
frequently used on custom mob creations and a quite powerful tool; as it
allows for countless interesting applications. See the [potions
page](/Items/Potions) for a complete list of available potion
effects.

Potion effects are currently the only way to make mobs invisible, with
the exception of the armorstand mobtype which has it's own attribute for
indefinite invisibility. Extremely high modifier-levels may have obscure
effects.

Attributes
----------

| Attribute    | Aliases        | Description                                                                               | Default |
|--------------|----------------|-------------------------------------------------------------------------------------------|---------|
| type         | t              | The type of [potion effect](/Items/Potions) to apply.                           |         |
| duration     | d              | The duration of the effect in ticks [1].                                                  | 100     |
| level        | l              | The modifier-level of the potion effect. The real level is level's value +1. | 1       |
| force        |                | Whether not to override the current potion effect or not. (4.0+)                          | false   |
| hasParticles | particles or p | Whether not to show the status effect particles. (4.6+)                                   | true    |
| hasIcon      | icon or i      | Whether not to show the status effect icon. (4.6+)                                        | true    |

Examples
--------

This example skill-configuration will strongly slow down the target for
10 seconds (200 ticks) and deal 5 hearts of damage to it.

    Cripple:
      Skills:
      - potion{type=SLOW;duration=200;level=4}
      - damage{amount=10}

[1] 20 ticks = 1 second