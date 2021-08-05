**Description:** 

Shows the near world border effect. _Enable Fancy Graphics to see the effect._

---

**Attributes:**

| Attribute | Alias  | Description                                   | Default Value |
| --------- | ------ | --------------------------------------------- | ------------- |
| duration  | d      | The time (in ticks) that the effect is active | 20            |
| cancel    | c      | If true, it stops any existing redscreen      | false         |

---

**Examples:**

Shows red around the player screen

```
- effect:bloodyScreen{d=25} @PIR{r=15} ~onTimer:20
```