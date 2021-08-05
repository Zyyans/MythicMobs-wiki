**Description:** Checks the target's last damage cause

**Type:** Entity

---

**Attributes:**

| Attribute   | Alias    | Description               |
| ----------- | -------- | ------------------------- |
| damagecause | cause, c | The damage cause to match |

---

List of all possible damage causes: 

https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDamageEvent.DamageCause.html

---

**Examples:**

```
Conditions:
- lastdamagecause{c=ENTITY_ATTACK} true
```