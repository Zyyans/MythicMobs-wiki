**Description:** If the target location is not within the given WorldGuard region

**Type:** Location

---

**Attributes:**

| Attribute | Alias | Description     |
| --------- | ----- | --------------- |
| region    | r     | the region name |

---

**Examples:**

```
Conditions:
- notinregion{r=BossZone} true
```