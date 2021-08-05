Mechanic: SetTargetScore
========================

*Added in version 2.3*

Modifies the a scoreboard-objective value of the specified targeter(s).
Works exactly like the ModifyTargetScore-mechanic, but is only capeable
of performing the **set**-action.

Attributes
----------

| Attribute | Aliases | Description                                                                                                                      | Default |
|-----------|---------|----------------------------------------------------------------------------------------------------------------------------------|---------|
| objective | obj, o  | Specifies the scoreboard objectiv to be changed. If the objective doesn't exist it will automatically be created by the mechanic |         |
| value     | v       | The value to perform the operation with                                                                                          |         |

  
Examples
----

This example will track how often and whom damaged
the casting mob in battle.

      Skills:
      - settargetscore
          {
          objective=damagescore;
          value=1
          } @trigger ~onDamaged
