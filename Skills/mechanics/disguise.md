Mechanic: Disguise
==================

Runs a disguise string on the casting mob. This skill requires Libs'
Disguises and ProtocolLib be installed to enable Disguise functionality.

See [Add-On: Disguises](/addons/disguises/start) for a list of available
disguises.

As of 4.12 Disguise mechanic got an overhaul and allows for direct command strings from LibsDiguises to work inside of its disguise attribute. The old way was renamed disguiseOld and the new way is disguise!

If you are on a version older then 4.12, then the old way is all that exists and it is still - disguise{} instead of - disguiseOld{}!

Attributes
----------

Any [disguise-specific
options](http://mythicmobs.net/manual/doku.php/addons/disguises/start#options)
can also be used as an attribute in the skill.

| Attribute | Aliases | Description                       | Default |
|-----------|---------|-----------------------------------|---------|
| disguise  | d, type | The disguise to apply to the mob. |         |

  

Examples
--------

**New Way**

you can test cast both of these disguises with ``/mm test cast TestingDisguiseMechanic``

This will disguise you as a sheep that is on fire and spinning. It will also set the disguises custom name to DizzyBoi and make it visible!
```
TestingDisguiseMechanic:
  Skills:
  - disguise{d="Sheep SetBurning SetSpinning SetCustomNameVisible setCustomName DizzyBoi"} @self
```

This next example will turn you into a steve head that glides across the floor. No good way to describe it. It is pretty funny. I recommend you try it out!

```
TestingDisguiseMechanic:
  Skills:
  - disguise{d="Zombie setYModifier -1.5 setPitchLocked setInvisible setHelmet PLAYER_HEAD"} @self
```

---------
**Old Way**

This example would cause the mob to turn into a sheep.

      Skills:
      - disguiseOld{d=SHEEP}

Configure custom disguises using Lib's Disguises for more granular detail.

---------