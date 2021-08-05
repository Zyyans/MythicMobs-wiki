Mechanic: Equip
===============

Equips the mob with an item. Uses the exact same syntax as the
[Equipment](/mobs/equipment) configuration.

Attributes
----------

| Attribute | Aliases | Description                               | Default |
|-----------|---------|-------------------------------------------|---------|
| item      | i       | The item config string to run on the mob. |         |

Examples
----
This example would equip the casting mob with a diamond sword.

    EquipDiamondSword:
      Skills:
      - equip{item=diamond_sword:0}

This example would equip the Skeleton King's crown as a helmet.

    EquipCrown:
      Skills:
      - equip{item=KingsCrown:4}
