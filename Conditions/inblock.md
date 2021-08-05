**Description:** Checks the material at the target location

**Type:** Location

---

**Attributes:**

| Attribute | Alias     | Description               |
| --------- | --------- | ------------------------- |
| block     | blocks, b | A list of blocks to match |

---

Valid for any Bukkit material type.

https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html

---

**Examples:**

```
Conditions:
- inblock{b=WATER,LAVA} false
```