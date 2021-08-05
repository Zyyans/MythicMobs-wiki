Mechanic: VariableMath
======================

Sets a variable to the result of a math equation, where 'x' is the
[variable](/skills/variables)'s current value.

Attributes
----------

| Attribute | Aliases | Description                                     | Default Value |
|-----------|---------|-------------------------------------------------|---------------|
| var       |         | The name and scope of the variable              |               |
| equation  | eq, e   | The operation to be done, must be inside quotes |               |

  
Examples
----

Storing a placeholder in a variable

    MMOVar:
      Skills:
      - variableMath{var=target.exp;equation="%mmocore_level%"}

Doing math

    Math1:
      Skills:
      - variableMath{var=caster.damage;equation="<caster.hp>*5"}
    Math2:
      Skills:
      - variableMath{var=caster.speed;equation="(<caster.var.age>/5)+1"}
