Mechanic: Animate ArmorStand
============================

Animates an armorstand.

Attributes
----------

| Attribute   | Aliases | Description                                                                             | Default Value |
|-------------|---------|-----------------------------------------------------------------------------------------|---------------|
| duration    | d       | How long the animation takes                                                            | 1             |
| smart       |         | Will help you to make your animations smoother if true                                  | true          |
| ignoreempty |         | Will ignore unspecified body parts and not animate them                                 | true          |
| usedegrees  |         | Interprets the input' values as degrees (0-360) and as radians (0-6.28) if set to false | true          |

  

Examples
--------

    Skills:
    - animatearmorstand{d=10;leftarm=90,0,0;rightarm=270,0,0;ignoreempty=false}
    - ...
