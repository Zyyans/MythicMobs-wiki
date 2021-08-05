Mechanic: Command
=================

Executes a command for each target supplied.

Color codes and variables are allowed. For a list of color codes look
[here](/databases/misc/colorcodes). Variables can be found
[here](/skills/stringvariables).

The command specified will not function correctly if it contains double
quotes " or curly brackets {} and must be substitued with their
respective [message variables](/skills/stringvariables). For a more
in-depth tutorial on how to use command-skills see [command-skills
tutorial](/tutorials/commandskills). That happens because the double
quotes and curly brackets are reserved for MythicMobs itself trying to
read the syntax you supplied.
`Update: as of MythicMobs 2.4 curly brackets {} do not need to be replaced with message variables anymore. Double quotes " however, still need replacements.`

Attributes
----------

| Attribute     | Aliases | Description                                                              | Default |
|---------------|---------|--------------------------------------------------------------------------|---------|
| command       | c       | The command to execute                                                   |         |
| asCaster      | ac      | If true the command will execute from the caster instead of the console. | false   |
| asOp          | op      | Whether to execute the command with all permissions                      | false   |
| asTarget      | at      | Executes the command as the skill target                                 | false   |
| requireTarget | rt      | Only executes if the skill has a target                                  | false   |

  

Examples
--------

### Correctly written command-skills

    Skills:
    - command{c="give <target.name> gold_ingot 20"} @trigger ~onInteract
    - command{c="minecraft:tp <target.name> <mob.uuid>"} @self ~onDamaged
    - command{c="minecraft:summon Zombie ~ ~ ~ <&lc>NoAI:true,CustomName:<&dq>Summoned Zombie<&dq><&rc>"}
    - command{c="minecraft:summon Zombie ~ ~ ~ {NoAI:true,CustomName:<&dq>Summoned Zombie<&dq>}"}

### Invalid command-skills

The below example(s) won't work because certain symbols haven't been
substituted with message variables.

    Skills:
    - command{c="minecraft:summon Zombie ~ ~ ~ {NoAI:true,CustomName:"Summoned Zombie"}"}

Tutorials
---------

-   [Villager trades using cmd-mechanics by
    Krowerom](https://www.youtube.com/watch?v=p71bl_W3a4I&feature=youtu.be)