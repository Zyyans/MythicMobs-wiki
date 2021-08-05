**Description:** checks the ender dragon phases

**Type:** Entity

---

**Attributes:**

| Attribute  | Alias  | Description                          |
| ---------- | ------ | -----------------------------------  |
| phases     | phase  | the ender dragon phases to check for |

---

**Examples:**

```
Conditions:
- enderdragonphase{phase=CIRCLING} true
```

```
Conditions:
- enderdragonphase{phases=FLY_TO_PORTAL,LEAVE_PORTAL} true
```

List of ender dragon phases: https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EnderDragon.Phase.html