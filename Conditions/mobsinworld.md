**Description:** Matches a range to how many mobs are in the target world

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
- mobsinworld{a=20to50} true
```

```
Conditions:
- mobsinworld{a=<50} true
```