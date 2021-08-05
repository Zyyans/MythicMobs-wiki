**Description:** This condition tests the material type present at the target location.

---

**Attributes:**

| Attribute | Aliases | Description                  |
| --------- | ------- | ---------------------------- |
| types     | type, t | A list of materials or MMOItem's block name to check |

Valid for any Bukkit material type.
https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html

---

**Examples:**

```
Conditions:
- blocktype{type=dirt} true
```

---

**Extra Information:**

- [x] Type: Location