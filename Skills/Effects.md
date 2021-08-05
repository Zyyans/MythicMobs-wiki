Skill Effects
-------------

Skill Effects (or effect mechanics) are a special type of mechanic
specifically designed to create special effects. These are called just
like any other [skill mechanic][] in your mob's Skill List, or you can
add them to your own skills and even combine them.

Most effects are able to target both Entities and Locations. You control
what your effect targets using a [Targeter][].

Audience `audience=World` or `audience=Target` can be used to only display the effects to a specific group, rather than the entire Server. This can be useful in preventing too many particles from being displayed to everyone which can cause lag.

### Syntax

A lot of effects don't have any options. To call them, you just call the
skill **effect:name**

    Skills:
    - effect:flames @target
    - effect:lightning @self
    - effect:ender @PlayersInRadius{r=20}
    - effect:ender @PlayersInRadius{r=20}
    - effect:particles{particle=reddust;color=#EE22CC;amount=10;speed=1;hS=0.15;vS=.15;audience=Target} @target

### Effects

| Effect Mechanic      | Description                                                           |
|----------------------|-----------------------------------------------------------------------|
| [Black Screen][]     | Blacks out the target's screen for the duration                       |
| [Block Mask][]       | Temporarily masks a block as a different block                        |
| [Block Unmask][]     | Unmasks blocks that have been masked                                  |
| [Block Wave][]       | Creates a wave of blocks at the target location                       |
| [Bloody Screen][]    | Makes the target's screen glow red                                    |
| [Ender][]            | Causes the "Ender" effect                                             |
| [Ender Beam][]       | Creates the enderbeam effects at the target                           |
| [Explosion][]        | Causes an explosion effect                                            |
| [Firework][]         | Causes a firework explosion                                           |
| [Flames][]           | Causes the Mob Spawner flame effect                                   |
| [Geyser][]           | Creates a "geyser" of water or lava                                   |
| [Glow][]             | Gives the target the glow effect with different colors (req. GlowAPI) |
| [Item Spray][]       | Sprays temporary items around the target                              |
| [Lightning][]        | Causes a fake lightning strike                                        |
| [Particles][]        | Creates particle effects around the target                            |
| [Particle Box][]     | Draws a box of particles around the target                            |
| [Particle Line][]    | Draws a line of particle effects to the target                        |
| [Particle Orbital][] | Draws orbiting particle effects around the target                     |
| [Particle Ring][]    | Draws a ring of particles around the target                           |
| [Particle Sphere][]  | Draws a sphere of particles around the target                         |
| [Particle Tornado][] | Draws a persistent "tornado" of particles at the target               |
| [Skybox][]           | Alters the target's skybox                                            |
| [Smoke][]            | Creates a puff of smoke                                               |
| [Smoke Swirl][]      | Creates a persistent "swirl" of smoke                                 |
| [Sound][]            | Plays a sound effect from a resource pack                             |
| [Spin][]             | Causes the mob to spin                                                |
| [TotemOfUndying][]     | Plays the effect of a player resurrecting                             |

### EffectLib Effects

These effects require the plugin "EffectLib" to be installed to use.

Note: EffectLib was dropped in MM ver 4.11, they may still work with older versions however.

| Effect Mechanic     | Description                                           |
|---------------------|-------------------------------------------------------|
| [Atom][]            | Creates a representation of an atom around the target |
| [Particle Vortex][] | Draws a "vortex" of particles around the target       |
| [DNA][]             |                                                       |

  [skill mechanic]: /skills/mechanics/
  [Targeter]: /skills/targeters/
  [Black Screen]: /skills/effects/blackscreen
  [Block Mask]: /skills/effects/blockmask
  [Block Unmask]: /skills/effects/blockunmask
  [Block Wave]: /skills/effects/blockwave
  [Bloody Screen]: /skills/effects/bloodyscreen
  [Ender]: /skills/effects/ender
  [Ender Beam]: /skills/effects/enderbeam
  [Explosion]: /skills/effects/explosion
  [Firework]: /skills/effects/firework
  [Flames]: /skills/effects/flames
  [Geyser]: /skills/effects/geyser
  [Glow]: /skills/effects/glow
  [Item Spray]: /skills/effects/itemspray
  [Lightning]: /skills/effects/lightning
  [Particles]: /skills/effects/particles
  [Particle Box]: /skills/effects/particlebox
  [Particle Line]: /skills/effects/particleline
  [Particle Orbital]: /skills/effects/particleorbital
  [Particle Ring]: /skills/effects/particlering
  [Particle Sphere]: /skills/effects/particlesphere
  [Particle Tornado]: /skills/effects/particletornado
  [Skybox]: /skills/effects/skybox
  [Smoke]: /skills/effects/smoke
  [Smoke Swirl]: /skills/effects/smokeswirl
  [Sound]: /skills/effects/sound
  [Spin]: /skills/effects/spin
  [TotemOfUndying]: /skills/effects/totemOfUndying
  [Atom]: /skills/effects/atom
  [Particle Vortex]: /skills/effects/particlevortex
  [DNA]: /skills/effects/dna