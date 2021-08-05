**Description**: Checks the color of Sheeps, Shulkers, Cat (Type), Parrots (Variants), Horses, Llamas, and TraderLlamas.

**Type**: Entity

| attribute | aliases | description |
| --------- | ------- | ----------- |
|   color   | clr, c  | the color to check for |


**Examples**:
```yaml
mySkill:
  Conditions:
  - color{c=RED} true
  Skills:
  - mechanics
  - mechanics
```