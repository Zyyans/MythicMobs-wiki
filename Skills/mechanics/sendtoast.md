Mechanic: Send Toast
====================

Displays a "toast" message to all targeted players. Does nothing if the
target is not a player.

Attributes
----------

| Attribute | Aliases | Description                                                                         | Default Value  |
|-----------|---------|-------------------------------------------------------------------------------------|----------------|
| icon      | i       | The icon to send. Accepts any valid MATERIAL.                                       | diamond_sword |
| iconnbt   | nbt     | The NBT of the icon.                                                                | NONE           |
| message   | msg,m   | The message to send. Must be in double-quotes.                                      | NONE           |
| frame     | f       | The type of toast to send. MUST BE LOWERCASE. Options are: challenge, task or goal. | challenge      |

  

Examples
--------

      Skills:
      - sendtoast{icon=DIAMOND; iconnbt={CustomModelData:1};message="Kill a boss!";frame=challenge} @PlayersInRadius{r=10}
      - ...
