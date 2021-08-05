Mechanic: SetScore
==================

*Added in version 2.3*

Modifies the scoreboard-objective value of a fake player name. Works
like the [Modify Score](/skills/mechanics/modifyscore) mechanic, but is
only capable of performing the **set**-action.

Attributes
----------

| Attribute   | Aliases | Description                                                                                                                      | Default |
|-------------|---------|----------------------------------------------------------------------------------------------------------------------------------|---------|
| objective   | obj, o  | Specifies the scoreboard objectiv to be changed. If the objective doesn't exist it will automatically be created by the mechanic |         |
| value       | v       | The value to perform the operation with                                                                                          |         |
| name, entry | n, e    | The name of the fake player                                                                                                      | dummy   |

  
Examples
----

This example will set the score of a player named
"Bob" for the objective "TestScore", even if that player doesn't exist
on the server.  
It will create the objective if it does not currently exist.

      Skills:
      - setscore{o=TestScore;e=Bob;v=1} ~onInteract 

![](https://i.imgur.com/0HKvAUM.png)
