Mechanic: Delay
===============

Causes the current skill list to be delayed by X ticks.

Delay can also be used as syntax directly inside other skills by adding
"delay=TICKS", see example below.

Skill-delay and Syntax-delay do not function the same manner.

Examples
--------

      Skills:
      - ignite{ticks=60}
      - delay 60
      - explode

Also possible:

      Skills:
      - ignite{ticks=60;delay=80}
      - explode{delay=80}

or:

      Skills:
      - skill{skill=exampleskill;delay=200}
