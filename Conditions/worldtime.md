**Description:** Matches a range against the target location's world's time.

---

**Attributes:**

| Attribute | Aliases        | Description               |
| --------- | -------------  | ------------------------- |
| time| t| A range of time to check|

---

**Examples:**

```
  Conditions:
  - worldtime{t=0to6000} true
```