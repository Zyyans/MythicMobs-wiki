**Description:** Whether the distance between the caster and target is within the given range.

Can be a single number, a ranged value (20to40), or >10 <5, etc.

**Type:** Compare

---

**Attributes:**

| Attribute | Alias | Description           |
| --------- | ----- | --------------------- |
| distance  |   d   | The distance to match |

---

**Examples:**

```
TargetConditions:
- distance{d=<2}
```