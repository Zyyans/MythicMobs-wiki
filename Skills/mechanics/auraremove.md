Mechanic: Aura Remove
=====================

Removes an aura from the target.

Attributes
----------

| Attribute | Aliases                  | Description          | Default Value |
|-----------|--------------------------|----------------------|---------------|
| aura      | buff, debuff, name, b, n | The name of the aura |               |
| stacks    | s                        | The amount of stacks | Max stacks    |

----------

As of 4.12 MM:

You can now specify "ANY" to remove all auras from the target

Examples
--------

      Skills:
      - auraremove{aura=Ice;stacks=10} @self ~onTimer:200
      - ...
