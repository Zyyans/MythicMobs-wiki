Mechanic: Fly Aura
==================

Makes the player fly, similar to the /fly command. Can use any aura
attribute.

Attributes
----------

| Attribute | Aliases | Description          | Default Value |
|-----------|---------|----------------------|---------------|
| duration  | d       | Duration of the aura | 200           |

  

Examples
--------

      Skills:
      - fly{duration=100} @trigger ~onInteract
      - ...
