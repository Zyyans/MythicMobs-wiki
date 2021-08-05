**Description:** Tests if the target is within the given angle from where the caster is looking

**Type:** Compare

---

**Attributes:**

| Attribute | Alias | Description                      |
| --------- | ----- | -------------------------------- |
| angle     | a     | The angle of the FOV to check in |
| rotation  | r     | Rotates the FOV to check in      |

---

**Examples:**

```
TargetConditions:
- fieldofview{angle=90} true
```