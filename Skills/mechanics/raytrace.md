Mechanic: Raytrace
---------------------

Traces a ray to the target. [This is a premium-only mechanic.]
 
Attributes
----------

| Attribute       | Aliases | Description                                                                                        | Default Value |
|---------------------|------------------------|-------------------------------------------------------|------|
| entityskill         | eskill, es             | skill used if it hits an entity (?)                   |      |
| locationskill       | lskill, ls             | skill used if it hits a location(?)                   |      |
| maxdistance         | distance, md, d        | max distance to trace                                 | 50   |
| raywidth | rw, w     | Width of the ray traced| 0.2                                                   |      |
| ignorepassableblocks| ignorepassable, ip     | ignores collision of passable blocks (?)              | true |
| fluidcollisionmode  | fcm                    | enables collision with fluid blocks  (Never/always?)  | NEVER|
| accuracy            | ac, a                  | spread of the traced ray                              |1     |
| verticalnoise       | vn                     | vertical spread of the ray                            | 0    |
| horizontalnoise     | hn                     | horizontal spread of the ray                          | 0    |
| raytraceConditions  | rc, rcon, rconditions  | Conditions applied to the raytraced target | NONE |

Examples
--------
```
  - raytrace{
      entitySkill=[
        - damage{amount=20}
      ];
      locationSkill=[
        - particles{p=flame;a=20;s=0.2;hS=0.1;vS=0.1}
      ];
      raytraceConditions=[
        - samefaction false
      ]} @targetlocation ~onUse
```