Mechanic: SetStance
===================

Sets the "stance" attribute of the target Mythic Mob to the given
string. Does nothing if the target is not a Mythic Mob.

Attributes
----------

| Attribute | Aliases | Description                   | Default Value |
|-----------|---------|-------------------------------|---------------|
| stance    | s       | The string-name of the stance | default       |

  

Special Notes
-------------

This is used in conjunction with the **stance condition** (see
[Conditions](/conditions/start)) to create different stances or phases
for a mob, where they use different abilities. The stance condition will
match the current stance loosely, meaning if you set the stance to
"angry fiery explosive" the stance condition will be true for "stance
fiery".

Examples
--------

This skill would change the caster's phase to "bowphase"

    StanceChangeSkill
      Skills:
      - setstance{stance=bowphase} @self

This skill would only be usable when the caster had the stance
"bowphase"

    AnotherSkill:
      Conditions:
      - stance bowphase
     Skills:
      - ...some bow skills
