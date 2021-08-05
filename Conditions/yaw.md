**Description:** Checks the yaw of the target entity against a range.

---

**Attributes:**

| Attribute | Aliases        | Description               |
| --------- | -------------  | ------------------------- |
| yaw| y| The yaw to check for|

---

**Examples:**

```
  Conditions:
  - yaw{y=90to180} true
```

```
  Conditions:
  - yaw{y=>0} true
```