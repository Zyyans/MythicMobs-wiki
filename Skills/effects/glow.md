**Description:** 

Makes the target glow.

---

**Attributes:**

| Attribute | Alias  | Description                                       | Default Value |
| --------- | ------ | ------------------------------------------------- | ------------- |
| duration  | d      | The time (in ticks) that the effect is active     | 20            |
| color     | c      | The color of the glow                             | white         |

---

**Note**

This effect requires glowAPI to work for any color other then the default

---

**Examples:**

Makes players glow red.

```
- glow{d=20;color=RED} @PIR{r=15} ~onTimer:20
```