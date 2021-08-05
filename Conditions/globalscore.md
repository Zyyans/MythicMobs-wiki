**Description:** Checks a global scoreboard value

**Type:** Entity

---

**Attributes:**

| Attribute | Alias | Description        |
| --------- | ----- | ------------------ |
| objective | o     | The objective      |
| value     | v     | The value to match |

---

**Examples:**

```
Conditions:
- globalscore{o=KillCount;value=5} true
```