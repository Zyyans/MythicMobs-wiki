**Description:** Whether the target is within the given cuboid between location1 x location2

**Type:** Compare

---

**Attributes:**

| Attribute | Alias | Description |
| --------- | ----- | ----------- |
| location1 | loc1, l1, a | x,y,z coordinates for the 1st point. |
| location2 | loc2, l2, b | x,y,z coordinates for the 2nd point. |
| relative  | r           | Whether or not the coordinates should be relative to the caster |
| world     | None        | The world for the cuboid location to check. |
---

**Examples:**

```
TargetConditions:
- cuboid{location1=x,y,z;location2=x,y,z;world=world;relative=true}
```


