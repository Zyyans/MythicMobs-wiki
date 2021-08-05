**Description:** This condition checks if the target player has a permission. 

**Type:** Entity (Player)

---

**Attributes:**

| Attribute  | Alias | Description |
| ---------- | ----- | ----------- |
| permission | p     | The permission to check for. |

---

**Examples:**

```
Conditions:
- haspermission{p=permission.node.here} true

TargetConditions:
- haspermission{p=permission.node.here} true

TriggerConditions:
- haspermission{p=permission.node.here} true
```


