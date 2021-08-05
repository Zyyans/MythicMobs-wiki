**Description:** Checks how many mobs are in a given radius

**Type:** Location

---

**Attributes:**

| Attribute | Alias | Description                    |
| --------- | ----- | ------------------------------ |
| types     | t     | The types of mobs to check for |
| amount    | a     | The range of mobs to check for |
| radius    | r     | The radius to check            |

---

**Examples:**

```
Conditions:
- mobsInRadius{types=CoolZombie;amount=5to10;radius=15}
```