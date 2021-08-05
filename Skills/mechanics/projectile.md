Mechanic: Projectile
====================

The Projectile skill fires a meta-"projectile" that can be decorated
using particle and sound effects.  
It's great for creating complex, aesthetically pleasing skills, such as
shadow bolts, balls of ice, or even meteors.  
It has a lot of options(more than any other skill) and can be a bit of a
nightmare to jump into without knowing what you're doing.  
It will disappear after reached targeted entity or location.  
Doesn't work on **Minecraft below 1.13**(excluding 1.13) which using **MythicMobs above 4.11**(excluding 4.11)

Attributes
----------

| Attribute            | Aliases     | Description                                                                                                                                                                                             | Default Value     |
|----------------------|-------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
| onTick               | oT          | Meta-Skill executed every [interval] ticks at the projectile's origin location.                                                                                                                       | None              |
| onHit                | oH          | Meta-Skill executed when the projectile hits entities that allow be hit. Targets hit are inherited by the meta-skill.                                                                                                    | None              |
| onEnd                | oE          | Meta-Skill executed when the projectile ends.                                                                                                                                                           | None              |
| Type                 | t           | The "type" of projectile. Default projectiles are launched from the mob's location towards the target. METEOR type projectiles fall from the sky above the target.                                      | NORMAL            |
| Interval             | i           | How often (in ticks) the projectile updates its position                                                                                                                                                | 4                 |
| HorizontalRadius     | hRadius, hR | The horizontal radius entities will be hit in around the projectile.                                                                                                                                    | 1.25              |
| VerticalRadius       | vRadius, vR | The vertical radius entities will be hit in around the projectile.                                                                                                                                      | Horizontal Radius |
| Duration             | d           | The max duration (in ticks) the projectile will persist.                                                                                                                                                | 100               |
| MaxRange             | mr          | The maximum range (in blocks) the projectile will travel.                                                                                                                                               | 40                |
| Velocity             | v           | The velocity of the projectile                                                                                                                                                                          | 5                 |
| StartYOffset         | syo         | Start Y Offset - Lets you offset where on the casting mob the projectile shoots from.                                                                                                                   | +1                |
| StartFOffset         | sfo         | Start Forward Offset - How far in front of the mob the projectile starts                                                                                                                                | +1                |
| StartSideOffset      | sso         | Start Side Offset - How far to the side of the mob the projectile starts                                                                                                                                | 0                 |
| TargetYOffset        | tyo         | Target Y Offset - Lets you offset where on the target the projectile shoots at.                                                                                                                         | +1                |
| HorizontalOffset     | hO          | Horizontal Offset will rotate the projectile's horizontal starting velocity around a 360-degree axis.                                                                                                   | 0                 |
| VerticalOffset       | vO          | Vertical Offset will rotate the projectile's vertical starting velocity around a 360-degree axis.                                                                                                       | 0                 |
| HitPlayers           | hp          | Whether the projectile will only hit player.                                                                                                                                      | true              |
| HitNonPlayers        | hnp         | Whether the projectile will hit any entities(including caster but not players).                                                                                                                                      | false             |
| StopAtEntity         | sE          | Whether the projectile will stop upon hitting a targetable entity.                                                                                                                                      | true              |
| StopAtBlock          | sB          | Whether the projectile will stop upon hitting an opaque block.                                                                                                                                          | true              |
| HugSurface           | hs          | Whether or not the projectile should move along the ground.                                                                                                                                             | false             |
| HeightFromSurface    | hfs         | For NORMAL projectiles, how high above the surface the projectile should glide if HugSurface is set to TRUE. For METEOR projectiles, how high above the surface the projectile starts above the target. | 0.5               |
| PowerAffectsRange    | par         | Whether a mob's [power level](power level) affects the projectile's range.                                                                                                                              | true              |
| PowerAffectsVelocity | pav         | Whether a mob's [power level](power level) affects the projectile's velocity.                                                                                                                           | true              |
| gravity              | g           | Determines the gravity of the projectile; use fractions (0.1-0.2) for low gravity                                                                                                                       | 0                 |

  

Special Notes
-------------

**For the <u>onStart</u> Skill:** onStart skills work in a special way -
any buff or "special effect" mechanics fired by onStart that have a
duration (such as ParticleTornado) will attach to the projectile for
their duration, which allows for some interesting effects.

**For the <u>onTick</u> Skill:** using the **@origin** targeter will
cause any skills or effects to target the projectile's location. This is
the intended way to configure how the projectile looks.

**For the <u>onHit</u> Skill:** Any targets the projectile hits are
passed to the skill inherently. Any targeters you put in the onHit skill
will *override* these and cause your skill to likely not work as you
intend.

**For the <u>onEnd</u> Skill:** Special effects for the projectile's end
also use **@origin**. Also, If you want entities near the end-point of
the projectile to be hit in a certain way (such as a final large
fireball explosion) you can use the **@PlayersNearOrigin{r=[radius]}**
targeter.

**Types:**  
There are two types of projectiles, the normal variant and also the
Meteor variant.  
Meteor projectiles are created above the target, rather than at the mob
that is firing the projectile.  
Because of this, meteor projectiles cannot use certain attributes (which
ones are pending further testing).

Projectile Bullets
------------------

Projectile mechanics can now specify a bullet type that will represent
the projectile. No longer are projectiles just limited to particles!

These work with the projectile, missile, and orbital mechanics.

Bullet types available are:

-   **ARROW** - *projectile{bulletType=ARROW;...}*
-   **BLOCK** - *projectile{bulletType=BLOCK;material=STONE;...}*
-   **ITEM** - *projectile{bulletType=ITEM;material=STONE;...}*
-   **MYTHICITEM** - *projectile{bulletType=MYTHICITEM;material=MyMythicItem;...}*
-   **MOB** - *projectile{bulletType=MOB;mob=SkeletonKing;...}*

Yes, that's right, you can even shoot projectiles made up of other
Mythic mobs! Mobs shot with the projectile skill cannot be interacted
with, but will still use all their skills...

You can also use the new **bulletSpin=#** option to give your bullets
some spin.

Examples
--------

This example shoots a fast-moving ball of ice that damages and slows the
first entity it hits:  
**Mob File**  

    Mob:
      Type: SKELETON
      Skills:
      - skill{s=IceBolt} @target ~onTimer:100

**Skills File**  

    IceBolt:
      Skills:
      - projectile{onTick=IceBolt-Tick;onHit=IceBolt-Hit;v=8;i=1;hR=1;vR=1}
    IceBolt-Tick:
      Skills:
      - effect:particles{p=snowballpoof;amount=20;speed=0;hS=0.2;vS=0.2} @origin
    IceBolt-Hit:
      Skills:
      - damage{a=10}
      - potion{type=SLOW;duration=100;lvl=2}