**Description:** Whether the distance from the world's spawn point to the target is within the given range

**Type:** Location

---

**Attributes:**

| Attribute | Alias | Description           |
| --------- | ----- | --------------------- |
| distance  |   d   | The distance to match |

---

**Examples:**

```
Conditions:
- distancefromspawn{d=<100} true
```

```
Conditions:
- distancefromspawn{d=>50} true
```