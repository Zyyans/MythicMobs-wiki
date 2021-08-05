**Description:** Matches the block the target entity is standing on

**Type:** Location

---

**Attributes:**

| Attribute | Alias | Description         |
| --------- | ----- | ------------------- |
| material  | m     | A list of materials |

---

Valid for any Bukkit material type.

https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html

---

**Examples:**

```
TargetConditions:
- onblock{m=BEDROCK,OAK_LEAVES,ACACIA_FENCE} false
```

```
TargetConditions:
- onblock{m=DIRT,STONE,GRAVEL} true
```