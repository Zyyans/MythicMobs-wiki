Mechanic: Velocity
==================

Modifies the velocity of the targeted entity(s). May be used on players,
too. Useful for all sorts of things like true knockback resistance,
force-skills or simulated wind.

Attributes
----------

| Attribute | Aliases | Description                                                             | Default Value |
|-----------|---------|-------------------------------------------------------------------------|---------------|
| mode      | m       | The operation to perform. Can be SET, ADD, REMOVE, DIVIDE, or MULTIPLY. | SET           |
| velocityx | vx, x   | Velocity on the x-axis. Can be negative.                                | 1             |
| velocityy | vy, y   | Velocity on the y-axis. Can be negative.                                | 1             |
| velocityz | vz, z   | Velocity on the z-axis. Can be negative.                                | 1             |

  

Examples
--------

This example will stop all momentum of the casting mob upon taking
damage. The effect will only last until the mob decides to move again or
is moved by other sources.But still will be repulsed by Enchantment: **ARROW_KNOCKBACK**

    internal_mobname:
      Type: Zombie
      Skills:
      - velocity{m=set;x=0;y=0;z=0} @self ~onDamaged