Mechanic: VariableAdd
=====================

Adds an amount to a [variable](/skills/variables) on the specified
scope. Only works with numeric variable types.

Attributes
----------

| Attribute | Aliases | Description                        | Default Value |
|-----------|---------|------------------------------------|---------------|
| var       | v       | The scope and name of the varibale |               |
| amount    | a       |                                    | 1             |

  

Examples
--------

      Skills:
      - variableadd{var=skill.testVar;amount=1} ~onInteract
      - ...
