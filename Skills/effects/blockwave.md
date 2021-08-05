**Description:** 

Creates a wave of the specified blocks, with varying shapes, speeds and blocks.

Note that the blockwave effect will never actually change any blocks in the world and thus will never grief the environment in any way. The changes made this effect are purely cosmetic, no actual blocks are changed and everything will always return to its original state.

Added in 4.12:
- Added velocityX, velocityY, velocityZ, and ignoreAir options

---

**Attributes:**

| Attribute | Alias  | Description                              | Default Value |
| --------- | ------ | ---------------------------------------- | ------------- |
| material  | mat, m | The type of block used for the blockmask | gravel        |
| data      | dv     | The data value used for the material     | 0             |
| radius    | r      | The radius of the blockwave effect       | 0             |
| radiusy   | n      | The y radius of the blockwave effect     | 0             |
| duration  | d      | Duration of the effect in ticks          | 0             |
| shape     | s      | The shape of the effect (Sphere/Cube)    | sphere        |
| velocity  | v      | The speed of the effect                  | 10            |

---

Material must be the corresponding Bukkit-material name. A list of possible materials is below:

https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html

The data value is only needed for old minecraft server versions - For example: using data value 1 on dirt will create coarse dirt.

there are 20 ticks in 1 second, and setting duration to 0 will have an infinite duration. 

Sphere and Cube are the only shapes available.

---

**Examples:**

1. Creates a stone blockwave in a sphere shape starting at your self location.

```
- blockwave{duration=100;material=stone;radius=5;radiusY=5;velocity=10;shape=sphere} @selflocation
```