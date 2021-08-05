Mechanic: Bar Remove
====================

Removes a custom boss bar on the casting mob(cannot be player).

Attributes
----------

| Attribute | Aliases | Description              | Default Value |
|-----------|---------|--------------------------|---------------|
| name      | n       | The name of the bossbar. | infobar       |

  

Examples
--------

      Skills:
      - barRemove{name="MyBossBar"} @self ~onInteract
      - ...