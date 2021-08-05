Mechanic: DisguiseTarget
========================

Runs a disguise string on the target mob. This skill requires Libs'
Disguises and ProtocolLib be installed to enable Disguise functionality.

See [Add-On: Disguises](/addons/disguises/start) for a list of available
disguises.

Attributes
----------

| Attribute | Aliases | Description                          | Default |
|-----------|---------|--------------------------------------|---------|
| disguise  | d, type | The disguise to apply to the target. |         |

  

Examples
--------

This example would cause the target to turn into a sheep.

      Skills:
      - disguisetarget{d=SHEEP} @target

This one would turn it into a player using the skin of Notch and giving
it the display name *Jeb*. Color codes are useable in the nametag field.

      Skills:
      - disguisetarget{type=player;player=&7Jeb;skin=Notch} @target
