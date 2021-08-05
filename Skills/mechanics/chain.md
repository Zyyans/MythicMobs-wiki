Mechanic: Chain
===============

Chain allows you to make skills that bounce between targets, like a
"chain lightning" type skill.

BounceConditions are evaluated after each "bounce" of the skill. With
the example, if someone were on the other side of a wall from the mob
but you were standing in the doorway, it could bounce from you to them
since it bounced around the wall

It will only bounce to the same entity per cast once. Also every time
the skill bounces, the entity it is bouncing from will be the "origin"
in the skill and the inherited target of onBounce will be the next
entity it is bouncing to, so fromOrigin is your friend for making
effects!

Attributes
----------

| Attribute        | Aliases    | Description                                                                 | Default |
|------------------|------------|-----------------------------------------------------------------------------|---------|
| onBounce         | ob         | The skill that bounces between targets                                      |         |
| bounces          | b          | How many times the chain should bounce                                      | 2       |
| delay            | d          | The delay between bounces                                                   | 1       |
| radius           | r          | How far the skill will bounce to a new target                               | 5       |
| hitSelf          | hs         | Whether the chain should affect the caster                                  | false   |
| hitTarget        | ht         | Whether the chain should do the initial from the caster to the first target | true    |
| hitPlayers       | hp         | Whether the chain should bounce to players                                  | true    |
| hitNonPlayers    | hnp        | Whether the chain should bounce to non-players                              | false   |
| bounceConditions | conditions | Conditions applied to the bounce target                                     | NONE    |

  

Examples
--------

    Skills:
      - chain{
          bounces=5;
          bounceRadius=10;
          bounceDelay=1;
          hitSelf=false;
          hitPlayers=true; 
          hitNonPlayers=true;
          hitTarget=true;
          onBounce=[
            - effect:particleline{p=flame;fromOrigin=true}
          ];
          bounceConditions=[
            - inlineofsight
            - hasaura{aura=damageResist} false
          ];
        } @target ~onTimer:20
