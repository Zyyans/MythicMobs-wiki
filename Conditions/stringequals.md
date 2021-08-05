**Description:** Checks if value1 equals value2. Both values can use [variables ](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Variables)and placeholders.

---

**Attributes:**

| Attribute | Aliases        | Description               |
| --------- | -------------  | ------------------------- |
| value1| val1, v1|  |
| value2| val2, v2|  |

---

**Examples:**

```
  Conditions:
  - stringequals{val1="yes!";val2="yes!"} true
```
```
  Conditions:
  - stringequals{val1="%denizen_<player[<trigger.uuid>].item_in_hand.has_nbt[special_item]>%";val2="true"} true
```
Uses Denizen, PlaceholderAPI, and MythicMobs to check whether the item the player is holding has a Denizen NBT key of “special_item.” <trigger.uuid> is a MythicMobs placeholder that gets parsed before PlaceholderAPI parses the Denizen tag.
```
  Conditions:
  - stringequals{val1="%denizen_<player[<trigger.uuid>].item_in_hand.raw_nbt.get[mythic_type].after[string:]>%";val2="SomeMythicItem"} true
```