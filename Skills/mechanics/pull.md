Mechanic: Pull
==============

Pulls all targeted entities towards the caster with a base velocity,
increasing based on the distance of targets from the caster.

Attributes
----------

| Attribute | Aliases | Description                                                             | Default Value |
|-----------|---------|-------------------------------------------------------------------------|---------------|
| velocity  | v       | The base velocity of the pull.                                          | 1             |
| toOrigin  | to      | Wether or not the target should pulled towards the origin of the skill. | false         |

  

Special Notes
-------------

Targets are pulled much faster based on their distance from the caster.
The defined velocity is a "base" velocity, and the skill scales the
velocity based on distance to attempt to pull the entity directly to the
mob if it is possible based on the base velocity.

Examples
--------

    DeathGrip:
      Skills:
      - pull{velocity=10} @target

      - pull{v=6;to=true} @PIR{r=10}
