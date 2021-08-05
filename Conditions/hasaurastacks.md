**Description:** Tests if the target has the given range of stacks from an aura

**Type:** Entity

---

**Attributes:**

| Attribute | Alias   | Description                             |
| --------- | ------- | --------------------------------------- |
| auraName  | name, n | The name of the aura to check for       |
| stacks    | s       | The number/range of stacks to check for |

---

**Examples:**

```
Conditions:
- hasaurastacks{n=firedebuff;s=>3} true
```