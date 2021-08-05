Mechanic: VariableUnset
=======================

**Aliases:** varUnset, unsetVariable, unsetVar

Unsets a [variable](/skills/variables).

Attributes
----------

| Attribute | Aliases | Description                                                                                                                                                                                                        | Default Value |
|-----------|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| variable  | var     | The name of the variable. Can optionally be prefixed with **scope.**                                                                                                                                               |               |
| scope     | s       | The [scope](/skills/variables#variable_scopes) of the variable, e.g. where the variable will be located.                                                                                                           | SKILL         |

--------

This mechanic was added in 4.12

--------
 
Examples
----

This will unset the testing caster scope variable from the caster.

```
RemoveVariable:
  Skills:
  - variableUnset{var=caster.testing} @self
```

This will unset the testing caster scope variable from the caster as well.
```
RemoveVariable:
  Skills:
  - variableUnset{var=testing;scope=caster} @self
```