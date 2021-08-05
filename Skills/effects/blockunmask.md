**Description:** 

The blockunmask effect is used to revert blockchanges made by the blockmask effect. For instance, this effect can be used in a high radius after a mob has died in order to “clean up” the fake block updates sent. However this is not neccessary, because the fake block changes created by the blockmask effect will be reverted if a chunk is reloaded for a player (but will only revert for that player).

---

**Attributes:**

| Attribute | Alias | Description                              | Default Value |
| --------- | ----- | ---------------------------------------- | ------------- |
| radius    | r     | The radius of the blockmask effect       | 0             |
| shape     | s     | The shape of the effect                  | sphere        |

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