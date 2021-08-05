Mechanic: ModifyScore
=====================

*Added in version 2.3*

Modifies the scoreboard-objective value of a fake player name.  
Can also be used to modify a specific players score.

A list of possible operations for the action-syntax:

-   SET
-   ADD
-   SUBTRACT
-   MULTIPLY
-   DIVIDE
-   [1] MOD

Attributes
----------

| Attribute   | Aliases | Description                                                                                                                       | Default |
|-------------|---------|-----------------------------------------------------------------------------------------------------------------------------------|---------|
| objective   | obj, o  | Specifies the scoreboard objective to be changed. If the objective doesn't exist it will automatically be created by the mechanic |         |
| action      | a       | The operation to perform                                                                                                          | ADD     |
| value       | v       | The value to perform the operation with                                                                                           | 0       |
| name, entry | n, e    | The name of the player/fake player                                                                                                | dummy   |

  
Examples 
----

This example will add one to the score of a player
named "Bob" for the objective "TestScore", even if that player doesn't
exist on the server.  
It will create the objective if it does not currently exist.

      Skills:
      - modifyscore{o=TestScore;e=Bob;a=add;v=1} ~onInteract 

![](https://i.imgur.com/0HKvAUM.png)

[1] shorthand for "Modular Division"
