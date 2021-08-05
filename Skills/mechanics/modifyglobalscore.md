Mechanic: ModifyGlobalScore
===========================

*Added in version 2.3*

Modifies the scoreboard-objective value of the fake player _GLOBAL_.
This is a notarget skill and cannot affect any other players' score.

A list of possible operations for the action-syntax:

-   SET
-   ADD
-   SUBTRACT
-   MULTIPLY
-   DIVIDE
-   [1] MOD

Attributes
----------

| Attribute | Aliases | Description                                                                                                                      | Default |
|-----------|---------|----------------------------------------------------------------------------------------------------------------------------------|---------|
| objective | obj, o  | Specifies the scoreboard objectiv to be changed. If the objective doesn't exist it will automatically be created by the mechanic |         |
| action    | a       | The operation to perform                                                                                                         | ADD     |
| value     | v       | The value to perform the operation with                                                                                          |         |

  
Examples
----

    - modifyglobalscore
        {
        objective=someobjective;
        action=multiply;
        v=2
        } ~onAttack

[1] shorthand for "Modular Division"
