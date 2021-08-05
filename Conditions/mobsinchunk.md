**Description:** Matches a range to how many mobs are in the target location's chunk

**Type:** Location

---

**Attributes:**

| Attribute | Alias | Description               |
| --------- | ----- | ------------------------- |
| amount    | a     | The number range to match |

---

**Examples:**

```
Conditions:
- mobsinchunk{a=1to5} true
```

```
Conditions:
- mobsinchunk{a=<5} true
```