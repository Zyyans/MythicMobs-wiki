Mechanic: Skill
===============

Executes another meta-skill, which must be located in
*/MythicMobs/Skills*. The executed skill will inherit any targets if no
targeter is specified.

Syntax
------

    Skills:
    - skill{skill=AnotherSkill} @Target ~onAttack
    - skill{s=AnotherSkill} @Trigger ~onSpawn

Since version 2.2.0 most mechanics are run async by default. If you
experience trouble with any skills that worked fine in previous versions
of MythicMobs, you may try adding ";sync=true" as syntax which will
force the skill the be run sync again. This practice is also recommended
if you're working with extremely timing-sensitive skills, but rarely
needed.

The attribute "sync=true" will be inherited by any sub-skills and cannot
be set to *false* later in a skill-tree.

| Attribute | Shorthand | Description                                                         | Default |
|-----------|-----------|---------------------------------------------------------------------|---------|
| forcesync | sync      | Whether to force the skill to be run synchroniously with Minecraft. | false   |

*"forcesync" was added in version 2.2*

Cooldown
--------

Skill configurations are capable of utilizing cooldown, set in seconds.
Since version 2.2 it's also possible to provide cooldown values in
decimals. Add cooldown to your skills like this:

    internal_skillname:
      Cooldown: <seconds>
      Conditions:
      - condition
      - ...
      Skills:
      - mechanic{}
      - ...

Note that this only applies for skill configurations that are saved as
skill-files in */MythicMobs/Skills*. Cooldown can't be added to
mechanics called directly in mob configuration files.

Examples
--------

    Skills:
    - skill{s=AnotherSkill;sync=true} @Target ~onAttack
    - skill{s=ice_bolt;sync=true} @Target ~onTimer:100
    - skill{sync=true;s=flamethrower} @TargetLocation ~onTimer:200
    - skill:Onemechainc @Target ~onDamaged
    - skill
        {
        skill=leafs;
        sync=true
        }