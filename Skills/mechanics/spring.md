Mechanic: Spring
================

Creates a temporary "spring" of liquid at the target entity or location.

Attributes
----------

| Attribute | Aliases | Description                                  | Default Value |
|-----------|---------|----------------------------------------------|---------------|
| type      | t       | The type of spring. Can be "water" or "lava" | water         |
| duration  | d       | The duration (in ticks) the spring will last | 40            |

  

Special Notes
-------------

Liquid spread from the spring can and will destroy any blocks that are
normally destroyed by liquids. Use wisely.

Examples
--------

Creates a spring of water under the target for 5 seconds.

    Flood:
      Skills:
      - spring{d=100} @target
