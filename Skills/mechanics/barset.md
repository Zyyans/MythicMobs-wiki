Mechanic: Bar Set
=================

Modifies a custom boss bar on the casting mob(cannot be player).

Attributes
----------

| Attribute | Aliases | Description                                             | Default Value               |
|-----------|---------|---------------------------------------------------------|-----------------------------|
| name      | n       | The name of the bossbar.                                | infobar                     |
| display   | d       | The text displayed on the bar.                          | &lt;skill.var.aura-name&gt; |
| value     | v       | How filled the bossbar is. Must be between 0.0 and 1.0. | 1.0                         |

  

Examples
--------

    Skills:
    - barSet{name="MyBossBar";display="<caster.name> - <caster.hp>";value=1.0} @self ~onDamaged
    - ...