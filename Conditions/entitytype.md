**Description:** Tests the entity type of the target

**Type:** Entity

---

**Attributes:**

| Attribute | Alias    | Description                     |
| --------- | -------- | ------------------------------- |
| type      | types, t | A list of entity types to match |

---

**Examples:**

```
Conditions:
- entitytype{t=ZOMBIE} true
```

```
TargetConditions:
- entitytype{t=WITCH} true
```

```
TriggerConditions:
- entitytype{t=PLAYER} true
```