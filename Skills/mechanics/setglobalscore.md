Mechanic: SetGlobalScore
========================

*Added in version 2.3*

Modifies the scoreboard-objective value of the fake player _GLOBAL_.
This is a notarget skill and cannot affect any other players' score.
Works exactly like the ModifyGlobalScore-mechanic, but is only capeable
of performing the **set**-action.

Attributes
----------

| Attribute | Aliases | Description                                                                                                                      | Default |
|-----------|---------|----------------------------------------------------------------------------------------------------------------------------------|---------|
| objective | obj, o  | Specifies the scoreboard objectiv to be changed. If the objective doesn't exist it will automatically be created by the mechanic |         |
| value     | v       | The value to perform the operation with                                                                                          |         |

  
Examples
----

    - setglobalscore
        {
        objective=someobjective;
        v=2
        } ~onAttack
