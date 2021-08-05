**Description:** Checks if the given numeric variable is within a certain range.

---

**Attributes:**

| Attribute | Aliases        | Description               |
| --------- | -------------  | ------------------------- |
| value| val, v| A number range to match|

---

**Examples:**

```
  TargetConditions:
  - variableInRange{var=target.fear;value=>20} cancel
  Skills:
  - message{m="&7You feel very afraid..."}
```