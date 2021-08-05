Mechanic: RemoveHeldItem
========================

Removes the given amount from the target's held item. This is an
artifacts-only mechanic.

Attributes
----------

| Attribute | Aliases | Description | Default Value |
|-----------|---------|-------------|---------------|
| amount    | a       |             | 1             |

Examples
--------

      Skills:
      - consumeHeldItem{amount=1} ~onUse
      - ...

If consumeHeldItem does not work for you, try using consumeUsedItem!
