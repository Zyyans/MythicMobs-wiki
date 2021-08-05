Mechanic: Shoot Fireball
========================

Shoots a fireball from the mob towards the target entity or location.

Attributes
----------

| Attribute     | Aliases   | Description                                                                    | Default Value |
|---------------|-----------|--------------------------------------------------------------------------------|---------------|
| yield         | y         | The yield (power) of the fireball's explosion.                                 | 1             |
| velocity      | v         | The velocity of the fireball.                                                  | 1             |
| incendiary    | i         | (true/false) Whether the fireball will leave behind fire.                      | false         |
| fireTicks     | ft        | How long (in ticks) fire left behind by the fireball will persist.             | 0             |
| smallfireball | small,sml | Whether or not to use the smaller blaze fireball instead of the ghast fireball | false         |
| playsound     | ps        | Whether or not to play the fireball launching sound when it is created         | false         |
| type          |           | SMALL/LARGE/DRAGON Added in MM 4.11 | SMALL |

  

Examples
--------

This example would shoot a barrage of 3 fast-moving fireballs at the
target.

    FireballBarrage:
      Skills:
      - shootfireball{y=1;v=4} @target
      - delay 10
      - shootfireball{y=1;v=4} @target
      - delay 10
      - shootfireball{y=1;v=4} @target
