**Description:** Checks if the target is holding a given material

**Type:** Entity

---

**Attributes:**

| Attribute | Alias   | Description                |
| --------- | ------- | -------------------------- |
| material  | m       | A material or MythicItem name to check for |

---

**Examples:**

```
# make sure to use ALL CAPS, otherwise the console
# will tell you it is not a valid material!!
Conditions:
- holding{m=DIAMOND_SWORD} true
```