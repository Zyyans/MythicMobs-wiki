Mechanic: Shoot Potion
======================

Throws a potion at the targeted entity or location, causing the splash
potion effect of the given type to all entities hit.

Attributes
----------

| Attribute    | Aliases        | Description                                                     | Default |
|--------------|----------------|-----------------------------------------------------------------|---------|
| type         | t              | The type of [potion effect](/databases/items/potions) to apply. | None    |
| duration     | d              | The duration of the effect, in ticks                            | 100     |
| level        | l              | The level of the potion effect                                  | 1       |
| velocity     | v              | The velocity of the thrown potion                               | 1       |
| hasParticles | particles or p | Whether not to show the status effect particles. (4.6+)         | true    |
| hasIcon      | icon or i      | Whether not to show the status effect icon. (4.6+)              | true    |

  

Examples
--------

    ThrownCripplingPotion:
      Skills:
      - shootpotion{type=SLOW;duration=200;level=4;velocity=5} @target
