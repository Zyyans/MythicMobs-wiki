Sets the immunity ticks on the target. This should be delayed if used immediately during an attack since the ticks are applied after an event completes.

**Attributes**

| Attribute | Alias | Description |
| --------- | ----- | ----------- |
| ticks     |       | the nodamageticks to set |

**Examples**
```
- setNoDamageTicks{ticks=0;delay=1} @trigger ~onAttack
```