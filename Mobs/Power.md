**Power Level**

Skill Power is an attribute available to all skills that increases the potency of skills. Base attributes set in the mob configuration will not be affected by power levels. It is primarily used as a way to increase skill power with a mob's level, and can only be applied using [Level Modifiers](/Mobs/Levels). Some mechanics have certain attributes that can be multiplied by power levels.

Future builds will allow you to define a scaling factor on it. In current builds it's not possible to turn off the affection of power levels when using mechanics except for the [Projectile](/skills/mechanics/projectile) and [Missile](/skills/mechanics/missile) mechanics. If you don't wish to utilize power levels simply do not use them in the level modifiers.

Mechanics that are affected by power levels + formulas:

| Mechanic      | Power Levels Effect                                   |
| ------------- | ----------------------------------------------------- |
| [basedamage](/skills/mechanics/basedamage) | {multiplier=M} - damage = M * power |
| [consume](/skills/mechanics/consume) | {damage=D} - damage = D * power |
| [consume](/skills/mechanics/consume) | {heal=H} - heal = H * power |
| [damage](/skills/mechanics/damage) | {amount=A} - damage = A * power |
| [leap](/skills/mechanics/leap) | {velocity=V} - velocity = V * ( 1 + power * 0.1 ) |
| [projectile](/skills/mechanics/projectile) | {velocity=V} - velocity = V * power |
| [projectile](/skills/mechanics/projectile) | {maxrange=MR} - maxrange = MR * power |
| [missile](/skills/mechanics/missile) | {velocity=V} - velocity = V * power |
| [missile](/skills/mechanics/missile) | {maxrange=MR} - maxrange = MR * power |

**Examples**

In this example, a Level 2 ThornySkeleton would do 10 damage instead of 5 because it gains +1 power per level (base power of 1 + 1 per level = 2, 5*2 = 10). A level 3 ThornySkeleton would do 15 damage, and so on.

```
ThornySkeleton:
  Type: SKELETON
  Health: 20
  LevelModifiers:
    Health: 10
    Power: 1
  Skills:
  - damage{a=5} @trigger ~onDamaged
```