**Description:** Checks the stance of the target mob.

---

**Attributes:**

| Attribute | Aliases        | Description               |
| --------- | -------------  | ------------------------- |
| stance| s| The stance to match|
| strict| str| Whether to match exactly. Defaults to false.|

---

**Examples:**

```
  Conditions:
  - stance{s=CombatStance;str=true} true
```