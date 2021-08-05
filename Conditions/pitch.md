**Description:** Checks if the pitch of the target entity is within a range

**Type:** Entity

---

**Attributes:**

| Attribute | Alias | Description               |
| --------- | ----- | ------------------------- |
| pitch     | p     | The number range to match |

---

**Examples:**

```
Conditions:
- pitch{p=-45to45} true
```

```
Conditions:
- pitch{p=>45} true
```