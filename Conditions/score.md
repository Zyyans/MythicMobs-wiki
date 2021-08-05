**Description:** Checks a scoreboard value of the target entity.

---

**Attributes:**

| Attribute | Aliases        | Description               |
| --------- | -------------  | ------------------------- |
| objective| o| The objective|
| entry| e| The entry|
| value| v| The value to match |

---

**Examples:**

```
  Conditions:
  - score{o=PlayerKills;e=Akim91;v=10} true
```