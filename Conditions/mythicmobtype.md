**Description:** Checks the MythicMob type of the target mob

**Type:** Entity

---

**Attributes:**

| Attribute | Alias    | Description               |
| --------- | -------- | ------------------------- |
| type      | types, t | A list of MythicMob types |

---

**Examples:**

```
Conditions:
- mythicmobtype{t=CoolZombie,IceZombie,SnowZombie} true
```

```
TargetConditions:
- mythicmobtype{t=HotZombie,LavaZombie,FireZombie} true
```