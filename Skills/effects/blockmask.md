**Description:** 

Creates a mask of blocks around the specified target. The blocks created or changed by this effect will disappear or rather reset to their former state after the specified duration expired. Resetting the blocks at an earlier point in time can be achieved by using the blockunmask-effect (see example below).

Note that the blockmask effect will never actually change any blocks in the world and thus will never grief the environment in any way. The changes made this effect are purely cosmetic, no actual blocks are changed and everything will always return to its original state.

Bukkit material/block names can be acquired ingame. Simply hold the block you want to use for the effect in your hand and then use the command “/itemdb”. This command will output the bukkit-material info along with some other info, including the data value of the block. This command should work on any bukkit/spigot server.

---

**Attributes:**

| Attribute | Alias  | Description                              | Default Value |
| --------- | ------ | ---------------------------------------- | ------------- |
| material  | mat, m | The type of block used for the blockmask | gravel        |
| data      | dv     | The data value used for the material     | 0             |
| radius    | r      | The radius of the blockmask effect       | 0             |
| noise     | n      | Defines the randomness of the effect     | 0             |
| duration  | d      | Duration of the effect in ticks          | 0             |
| shape     | s      | The shape of the effect (Sphere/Cube)    | sphere        |
| noair     | na     | Mask no air blocks only                  | true          |
| onlyair   | oa     | Mask air blocks only                     | false         |

---

Material must be the corresponding Bukkit-material name. List of materials is below.

https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html

The data value is only needed for old minecraft server versions - For example: using data value 1 on dirt will create coarse dirt.

there are 20 ticks in 1 second, and setting duration to 0 will have an infinite duration. 

Sphere and Cube are the only shapes available.

---

**Examples:**

1. Creates a netherrack environment around the casting mob. Leaving the duration on 0 ticks will cause the blocks to stay in their new fake form until manual block updates are provided or players relog into the game.

```
- effect:blockmask{m=netherrack;r=5} @self ~onTimer:1200
```

2. Creates a layer of ice underneath the feet of all players within a 50 block radius, causing them to have a constantly slippery walk.

```
- effect:blockmask{m=ice;r=2;d=20} @PIR{r=50} ~onTimer:5
```

3. Will forcibly reverse all effects created by the blockmask effect in the specified radius. The blockunmask effect doesn't have any syntax options except for “radius”.

```
- effect:blockunmask{r=30}
```