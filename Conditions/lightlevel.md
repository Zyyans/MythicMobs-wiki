**Description:** Tests the light level at the target location

**Type:** Location

---

**Attributes:**

| Attribute | Alias | Description              |
| --------- | ----- | ------------------------ |
| level     | l     | The level range to match |

---

**Examples:**

```
Conditions:
- lightlevel{l=10} true
```

```
Conditions:
- lightlevel{l=>10} true
```

```
Conditions:
- lightlevel{l=1to10} true
```