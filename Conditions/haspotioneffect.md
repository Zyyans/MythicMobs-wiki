**Description:** Tests if the target entity has a potion effect

**Type:** Entity

---

**Attributes:**

| Attribute | Alias   | Description                         |
| --------- | ------- | ----------------------------------- |
| type      | t       | The potion effect type              |
| level     | lvl, l  | An optional level range to match    |
| duration  | d       | An optional duration range to match |

---

**Examples:**

```
Conditions:
- haspotioneffect{t=SLOW;l=0-2;d=0-9999} true
```

```
TargetConditions:
- haspotioneffect{t=Speed;l=0-9} true
```