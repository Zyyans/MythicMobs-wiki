Mechanic: setname
=================

Sets the display name of the target. May only work with mobs.

Examples
--------

      Skills:
      - setname{name=newmobname} @self ~onDamaged 1

Sets the name of the mob to "newmobname" when the mob is damaged.

```
MySkeleton:
  Type: Skeleton
  Display: 'Skeleton <caster.hp>/<caster.mhp><&heart>'
  Skills:
  - setname{name=<caster.name>;delay=2} @self ~onDamaged
  - setname{name=<caster.name>;delay=2} @self ~onTimer:10 ?incombat{}
```
This will set the name of the mob to the name it has in its Display: option when it is damaged and every 10 ticks when it is in combat. This is an example of how to make your mob update any placeholders in its name. In this example we are doing it to update the <caster.hp> placeholder.

As of Build 3070, this mechanic supports placeholders.