**Description:** 

Creates the effect of an Ender Crystal towards the target.

---

**Attributes:**

| Attribute | Alias  | Description                                       | Default Value |
| --------- | ------ | ------------------------------------------------- | ------------- |
| duration  | d      | The time (in ticks) that the effect is active     | 60            |
| yoffset   | y, yo  | 	The default vertical offset from the casting mob | 0             |

---

  **Note**
  
  The enderbeam skill also creates an ender crystal at the mobs position.

**Examples:**

This creates an enderbeam effect at the mobs target for 5 seconds, and is offset by 2 blocks from the casting mob.

```
- effect:enderbeam{d=100;y=2} @target
```