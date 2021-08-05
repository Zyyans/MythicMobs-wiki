Mechanic: Bar Create
====================

Creates a custom boss bar on the casting mob(cannot be player).

Attributes
----------

| Attribute | Aliases | Description                                                                                                         | Default Value               |
|-----------|---------|---------------------------------------------------------------------------------------------------------------------|-----------------------------|
| name      | n       | The name of the bossbar.                                                                                            | infobar                     |
| display   | d       | The text displayed on the bar.                                                                                      | &lt;skill.var.aura-name&gt; |
| value     | v       | How filled the bossbar is. Must be between 0.0 and 1.0.                                                             | 1.0                         |
| color     | c       | The color of the bossbar. Accepts the following: PINK, BLUE, RED, GREEN, YELLOW, PURPLE, WHITE.                     | RED                         |
| style     | s       | The style of the bossbar. Accepts the following: SOLID, SEGMENTED_6, SEGMENTED_10, SEGMENTED_12, SEGMENTED_20 . | SOLID                       |

  

Examples
--------

      Skills:
      - barCreate{name="MyBossBar";display="<caster.name> - <caster.hp>";value=1.0;color=BLUE;style=SEGMENTED_6} @self ~onSpawn
      - ...