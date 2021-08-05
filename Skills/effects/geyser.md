**Description:** 

Causes a geyser of liquid to shoot out of the ground at the targeted entity or location.

---

**Attributes:**

| Attribute | Alias  | Description                                       | Default Value |
| --------- | ------ | ------------------------------------------------- | ------------- |
| type      | t      | The type of liquid. Can be “water” or “lava”      | water         |
| height    | h      | How high the geyser will go                       | N/A           |
| speed     | s      | The speed (in ticks) of the geyser animation      | 10            |

---

**Examples:**

```
- effect:geyser{type=LAVA;height=3;speed=10}
```