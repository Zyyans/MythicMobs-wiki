Mechanic: Set Gravity
=====================

Sets whether gravity affects the target entity.

Attributes
----------

| Attribute | Aliases | Description                                     | Default Value |
|-----------|---------|-------------------------------------------------|---------------|
| gravity   | g       | Sets whether the entity uses gravity (boolean). | true          |

  

Examples
--------

      Skills:
      - setgravity{g=false} @self ~onSpawn
      - ...
