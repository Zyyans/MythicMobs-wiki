**Description:** This condition checks if the target entity is wearing the selected item.  

**Note**:Doesn't work on **Minecraft below 1.13**(excluding 1.13),if u want to check item on Minecraft below 1.13,you can use MythicMobsExtension's Condiiton: '''ownsitem'''

**Type:** Entity

---

**Attributes:**

| Attribute | Alias     | Description |
| --------- | --------- | ----------- |
| armorslot | slot, s   | The item slot to check. |
| material  | mmitem, m | A material or MythicItem name to check for. |
| checklore | cl        | Whether to strictly match item lore. |

**Valid Slots:**

| HEAD | CHEST | LEGS | FEET | HAND | OFFHAND |       
| ---- | ----- | ---- | ---- | ---- | ------- |  

**Aliases:**

| Condition Aliases |
| ----------------- | 
| iswearing         |
| wielding          |
| iswielding        |
---

**Examples:**

```
Conditions:
- wearing{slot=HAND;m=IRON_SWORD} true
```