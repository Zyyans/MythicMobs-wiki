Mechanic: Throw
===============

Throws all targets away from the mob (or origin).

Attributes
----------

| Attribute | Aliases | Description                                           | Default Value |
|-----------|---------|-------------------------------------------------------|---------------|
| velocity  | v       | The horizontal velocity at which the entity is throw. | 1             |
| velocityY | vy      | The vertical velocity at which the entity is thrown   | 1             |

  

Examples
--------

      GroundSlam:
        Skills:
        - effect:explosion @Self
        - damage{amount=10} @PlayersInRadius{r=5}
        - throw{velocity=15;velocityY=5} @PlayersInRadius{r=5}

In this example the mob will create an explosion effect around them that
inflicts 10 damage (5 hearts) to players within a radius of 5 blocks and
will knock them back. Giving the illusion of a powerful explosion.

Complex Examples
----------------

    SuperShockslam:
      Skills:
      - throw{velocity=5;velocityY=5} @PIR{r=10}
      - damage{a=50;i=false} @PIR{r=10}
      - effect:particles{p=hugeexplode;a=5;vs=0.5;hs=0.5;s=0;y=1} @Self
      - effect:sound{s=entity.generic.explode;v=2;p=0.5} @Self
      - effect:sound{s=entity.generic.explode;v=2;p=1;repeat=7;repeatInterval=2} @Self
      - effect:particlering{p=largeexplode;a=40;vs=0.5;hs=0.5;s=0;y=0.3;points=20;radius=1} @Self
      - delay 2
      - effect:particlering{p=largeexplode;a=40;vs=0.5;hs=0.5;s=0;y=0.3;points=20;radius=3} @Self
      - delay 2
      - effect:particlering{p=largeexplode;a=40;vs=0.5;hs=0.5;s=0;y=0.3;points=20;radius=5} @Self
      - delay 2 
      - effect:particlering{p=largeexplode;a=40;vs=0.5;hs=0.5;s=0;y=0.3;points=20;radius=7} @Self
      - delay 2
      - effect:particlering{p=largeexplode;a=40;vs=0.5;hs=0.5;s=0;y=0.3;points=20;radius=9} @Self
      - delay 2
      - effect:particlering{p=largeexplode;a=40;vs=0.5;hs=0.5;s=0;y=0.3;points=20;radius=11} @Self

This complex example shows how the throw mechanic can be used in
conjunction with other mechanics to make quite amazing effects. The
caster unleashes a powerful shockwave that deals 50 damage (25 hearts)
to all players within 10 blocks and using the **throw** mechanic causes
them to be flung a small bit into the air. There is also extra effects
added to make the attack more appealing to look at and intimidating.
