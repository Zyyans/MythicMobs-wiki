Mechanic: TeleportIn
====================
**Aliases:** tpin, tpdir, tpi

Will teleport the target relative to the caster's yaw. The direction attribute must be in this format: direction=x,y,z

`x` is forward or backward, `y` is up or down, and `z` is left or right

Attributes
----------

| Attribute             | Aliases   | Description                                                                   | Default Value |
|-----------------------|-----------|-------------------------------------------------------------------------------|---------------|
| vector | direction,dir,d,v | The direction to where the mob will be teleported                                 | |
| yaw | y | Yaw modifier | 0 | 
                
Examples
--------

Will teleport the player that triggered the skill to the right of the caster.

    Skills:
    - teleportin{vector=0,0,1} @trigger ~onInteract