Mechanic: Orbital
=================

The Orbital skill fires a special type of
[projectile](/skills/mechanics/projectile) that will orbit around the
target and can also act as an [Aura](/skills/mechanics/aura). Like the
projectile, it will trigger other skills on anyone that is hit by it
during its orbit.  
Much like projectile, it's great for creating complex skills, such as a
fire shield, and is a very complex skill to master.  

Added projectile bullets to Orbital in MM 4.11. See how to use them on the [projectiles mechanic](/skills/mechanics/projectile) page.

Attributes
----------

| Attribute           | Aliases  | Description                                                                                                                                                                       | Default Value |
|---------------------|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| onStart             | oS       | Meta-Skill executed when the orbital first starts.                                                                                                                                | None          |
| onTick              | oT       | Meta-Skill executed every [interval] ticks at the orbital's origin location.                                                                                                    | None          |
| onHit               | oH       | Meta-Skill executed when the projectile hits something. Targets hit are inherited by the meta-skill.                                                                              | None          |
| onEnd               | oE       | Meta-Skill executed when the projectile ends.                                                                                                                                     | None          |
| Charges             | c        | If set, the orbital will stop after firing this many times.                                                                                                                       | 0             |
| Duration            | d        | The max duration (in ticks) the orbital will persist.                                                                                                                             | 100           |
| Interval            | i        | How often (in ticks) the orbital updates its position                                                                                                                             | 4             |
| Radius              | r        | The radius of the orbit around the target.                                                                                                                                        | 4             |
| HitRadius           | hr       | The radius around the orbital that something will be hit.                                                                                                                         | 1             |
| VerticalHitRadius   | vhr, vr  | The radius around the orbital that something will be hit.                                                                                                                         | 1             |
| Points              | p        | How many "points" that comprise the circle that makes up the orbit. More points will make the circle more defined, but will also increase the time it takes to complete an orbit. | 32            |
| XRotation           | rotx, rx | Rotates the orbital along the X axis.                                                                                                                                             | 0             |
| YRotation           | roty, ry | Rotates the orbital along the Y axis.                                                                                                                                             | 0             |
| ZRotation           | rotz, rz | Rotates the orbital along the Z axis.                                                                                                                                             | 0             |
| XOffset             | ox       | Offsets the orbital along the X axis of the target.                                                                                                                               | 0             |
| YOffset             | oy       | Offsets the orbital along the Y axis of the target.                                                                                                                               | 0             |
| ZOffset             | oz       | Offsets the orbital along the Z axis of the target.                                                                                                                               | 0             |
| AngularVelocityX    | avx, vx  | Modifies the angular velocity of the orbital on the X axis.                                                                                                                       | 0             |
| AngularVelocityY    | avy, vy  | Modifies the angular velocity of the orbital on the Y axis.                                                                                                                       | 0             |
| AngularVelocityZ    | avz, vz  | Modifies the angular velocity of the orbital on the Z axis.                                                                                                                       | 0             |
| HitPlayers          | hp       |                                                                                                                                                                                   | true          |
| HitNonPlayers       | hnp      |                                                                                                                                                                                   | false         |
| HitSelf             | hs       |                                                                                                                                                                                   | false         |
| CancelOnGiveDamage  | cogd     |                                                                                                                                                                                   | false         |
| CancelOnTakeDamage  | cotd     |                                                                                                                                                                                   | false         |
| CancelOnDeath       | cod      |                                                                                                                                                                                   | true          |
| CancelOnTeleport    | cot      |                                                                                                                                                                                   | false         |
| CancelOnChangeWorld | cocw     |                                                                                                                                                                                   | false         |
| CancelOnSkillUse    | cosu     |                                                                                                                                                                                   | false         |
| CancelOnQuit        | coq      |                                                                                                                                                                                   | true          |

  

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

Examples
--------

This example puts an icy-looking orbital shield around the mob when it
is hit sometimes, that will last for 10 seconds or until it is triggered
once:  
**Mob File**  

    Mob:
      Type: SKELETON
      Skills:
      - skill{s=IceShield} @self ~onDamaged 0.2

**Skills File**  

    IceShield:
      Skills:
      - orbital{onTick=IceShield-Tick;onHit=IceShield-Hit;points=20;interval=1;duration=200;charges=1}
    IceShield-Tick:
      Skills:
      - effect:particles{p=snowballpoof;amount=20;speed=0;hS=0.2;vS=0.2} @origin
    IceShield-Hit:
      Skills:
      - damage{a=10}
      - potion{type=SLOW;duration=100;lvl=2}
