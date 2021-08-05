Mechanic: Set Game Mode
=======================

Sets the gamemode of the target player. Does nothing if the target is
not a player. Requires the `sync=true` attribute.

Attributes
----------

| Attribute | Aliases | Description                           | Default Value |
|-----------|---------|---------------------------------------|---------------|
| mode      | m       | The gamemode to change the target to. | SURVIVAL      |

  

Examples
--------

      Skills:
      - setgamemode{m=CREATIVE;sync=true} @PlayersInRadius{r=10} ~onSpawn
      - ...
