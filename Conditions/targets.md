**Description:** Tests if the number of inherited targets from the parent skilltree matches the given range.

---

**Attributes:**

| Attribute | Aliases        | Description               |
| --------- | -------------  | ------------------------- |
| amount| a| Range of how many targets to check for|

---

**Examples:**

```
  Conditions:
  - targets{a=>0} true
```

```
  Conditions:
  - targets{a=0to5} true
```