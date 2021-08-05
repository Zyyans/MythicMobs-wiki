Effect: Particles
----

Creates a particle effect at the targeted entity or location.

A list of particle types can be found [here](/skills/effects/particles/types).

Added in 4.11: 
* Added dir=x,y,z option to particle effects to specify directional vector
* Added audience=\[world/target/caster\] options to all particle effects

Added in 4.12 (Premium Only!):
* Added special type particle=mob on all particle effects
* You can then specify a MythicMob using mob=\[type\]
* This is a hacky way for you to use mobs as "particles" in effects using no-tick ArmorStands wearing models or using font characters. You can use things other than ArmorStands if you want, but we don't recommend it for performance.

### Attributes
----

#### General Attributes

| Attribute  | Aliases | Description | Default Value |
| ------ | ------ | ------ | ------ |
| particle  | p  | The particle type to use. See list here.  | reddust |
| material | m | Block or Item to use with block_crack or item_crack respectively (1.13+) |
| amount | a | The number of particles to create | 10    |
| hSpread | hs  | The horizontal spread of the particles | 0     |
| vSpread | vs  | The vertical spread of the particles | 0     |
| speed | s   | The “speed” of the particles | 0 |
| yOffset | y   | The Y offset of the particles from the target | 0 |
| viewDistance | vd  | The distance the particles are rendered | 128   |
| Size | | The size of the particles displayed | 1 |
| color | c | [(1)](/wikis/skills/effects/particles "only works on colorable particle types like “reddust”")[(2)](/wikis/skills/effects/particles "color must be provided in hex-code") The color of the particle The color of the particle |  |
| fromorigin |  |  | false |
| directional | d | Causes the particles to move at # speed. Direction is based on origin and caster. | false | 
| directionReversed | | Reverses the direction of the particles. | false | 
| direction | dir | Specifies a coordinate for the particles to move towards. | None | 

The “color” attribute was added in version 2.3

#### Entity-Only Attributes

| Attribute       | Aliases  | Description | Default Value |
|-----------------|----------|------|---------------|
| useEyeLocation | uel | (true/false) Whether to base the particles on the entity's eyes | false |
| forwardOffset   |  | The forward-offset from the targeted entity,doesn'n work when set directional to true | 0 |
| sideOffset | so | The side-offset from the targeted entity,doesn'n work when set directional to true | 0 |

#### Particle Colors

As of MythicMobs version 2.3, some particles effects (mobSpell, mobSpellAmbient, and reddust) can be colored by using an additional “color=hexcode” argument. Hexcodes for coloring particles can be found here: [Hex Colors](http://www.color-hex.com/) From MM Version 2.5.0+ and Minecraft version 1.10 onwards, fallingdust also may use the color option.

    - effect:particles{p=reddust;color=#FF00FF}

### Examples
----
    Skills:
    - effect:particles{particle=flame;amount=200;hS=1;vS=1;speed=5} @self
    - ...
1.12 block_crack

    Skills:
    - effect:particles{particle=block_crack_dirt_0;amount=100;hS=1;vS=1} @self

1.13 block

    Skills:
    - effect:particles{particle=block;m=dirt;amount=100;hS=1;vS=1} @self