**Skill Parameters**
====================

Skill parameters are a new feature allowing you to more easily create generic skills and pass parameters to them from other skills. If that sounds confusing, here's an example!

Currently most people have a lot similar damage skills that are just tweaked a bit for all their different mobs for slight variances in damage, but they do basically the same thing otherwise.

Make sure to use all lowercase in your skill parameters! Testing this lead to getting errors when using any capital letters. It works fine when using all lowercase parameter names!

**The old way of doing it:**

------------------

```
ShadowDamage20:
  Skills:
  - damage{amount=20}
  - some shadowy effect

ShadowDamage50:
  Skills:
  - damage{amount=50}
  - some shadowy effect

Mob1:
  Skills:
  - skill:ShadowDamage20 ~onAttack

Mob2:
  Skills:
  - skill:ShadowDamage50 ~onAttack
```

-----------------

**With Skill Parameters, we can combine these all into a single skill! The new way:**

-----------------

```
ShadowDamage:
  Skills:
  - damage{amount=<skill.damage>}

Mob1:
  Skills:
  - skill:ShadowDamage{damage=20} ~onAttack

Mob2:
  Skills:
  - skill:ShadowDamage{damage=50} ~onAttack
```

----------------

The "skill parameter" system will pass any options from the skill/metaskill mechanic (except options that are specific to it) down the skill tree where you can reference them later. If a later skill passes the same parameter, it will overwrite it. These can be used anywhere placeholders are supported.

----------------

```
- skill{skill=SomeSkill;anything=2;somethingElse=5}

SomeSkill:
  Skills:
  - particles{amount=<skill.anything>}
  - damage{amount=<skill.somethingElse>}
```