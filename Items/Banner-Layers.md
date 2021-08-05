Banner Layers
=============

<img src="http://fs5.directupload.net/images/160306/4jggyj4s.jpg" width="500" height="200" alt="http://fs5.directupload.net/images/160306/4jggyj4s.jpg" />

To make complex banner items in MythicMobs, you can use the following syntax. There is no hard limit placed by MythicMobs on the number of banner layers you can use and you can go past the vanilla maximum of 6 layers set by Minecraft using this. However going past 6 layers may cause unusual behavior and/or lag.

Banner layers are also applicable to shields.

Syntax
------
```
Banner:
  Id: <banner/shield>
  Options:
    Color: <BASE COLOR>
  BannerLayers:
  - <color> <pattern>
  - <color> <pattern>
```
Patterns
--------

| **Patterns**             |                       |
|--------------------------|-----------------------|
| BASE                     | SQUARE\_BOTTOM\_LEFT  |
| BORDER                   | SQUARE\_BOTTOM\_RIGHT |
| CIRCLE\_MIDDLE           | SQUARE\_TOP\_LEFT     |
| CREEPER                  | SQUARE\_TOP\_RIGHT    |
| CROSS                    | STRAIGHT\_CROSS       |
| CURLY\_BORDER            | STRIPE\_BOTTOM        |
| DIAGONAL\_LEFT           | STRIPE\_CENTER        |
| DIAGONAL\_LEFT\_MIRROR   | STRIPE\_DOWNLEFT      |
| DIAGONAL\_RIGHT          | STRIPE\_DOWNRIGHT     |
| DIAGONAL\_RIGHT\_MIRROR  | STRIPE\_LEFT          |
| FLOWER                   | STRIPE\_MIDDLE        |
| GRADIENT                 | STRIPE\_RIGHT         |
| GRADIENT\_UP             | STRIPE\_SMALL         |
| HALF\_HORIZONTAL         | STRIPE\_TOP           |
| HALF\_HORIZONTAL\_MIRROR | TRIANGLE\_BOTTOM      |
| HALF\_VERTICAL           | TRIANGLE\_TOP         |
| HALF\_VERTICAL\_MIRROR   | TRIANGLES\_BOTTOM     |
| MOJANG                   | TRIANGLES\_TOP        |
| RHOMBUS\_MIDDLE          |                       |
| SKULL                    |                       |

Examples
--------
```
testbanner:
  Id: banner
  Display: '&rBanner of Test'
  Options:
Color: 0,0,0
  BannerLayers:
  - GRAY DIAGONAL_RIGHT
  - RED GRADIENT
  - YELLOW GRADIENT_UP
  - WHITE BORDER
  - BLACK SKULL
  - RED SKULL
  - ORANGE SKULL
  - YELLOW SKULL
```
```
SkeletonKingBanner:
  Id: banner
  Display: '&4Skeleton King<&sq>s Banner'
  Options:
    Color: RED
  BannerLayers:
  - WHITE CURLY_BORDER
  - WHITE STRIPE_CENTER
  - BLACK STRIPE_BOTTOM
  - WHITE CREEPER
  - YELLOW STRIPE_TOP
  - BLACK TRIANGLES_TOP
```
