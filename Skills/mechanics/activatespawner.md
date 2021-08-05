Mechanic: Activate Spawner
--------------------------

Activates a MythicMobs spawner, causing it to spawn mobs. Will not
override any conditions or options set on the spawner.

Attributes
----------

| Attribute | Aliases    | Description                                                                                                    | Default Value |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| spawners  | spawner, s | The name of the spawner(s) to activate. This can accept groups and wildcards also using the appropriate syntax | NONE          |

  

Special Notes
-------------

Best used in conjunction with setting the "useTimer" attribute on
spawners to "false".

Examples
--------

This would activate the spawner named "BossAdd"

    Skills:
    - activatespawner{spawner=BossAdd}

This example would activate all spawners in the group "Castle"

    Skills:
    - activatespawner{spawner=g:Castle}

This example would activate all spawners starting with
"DungeonBoss1Spawner" (i.e. DungeonBoss1Spawner1, DungeonBoss1Spawner2,
etc)

    Skills:
    - activatespawner{spawner=DungeonBoss1Spawner*}
    - ...
