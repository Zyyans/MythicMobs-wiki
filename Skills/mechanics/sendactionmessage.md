Mechanic: ActionMessage
=======================

![](http://fs5.directupload.net/images/160306/zswobuo8.jpg)

Sends a message to the target player's action bar.

[Color codes](/databases/misc/colorcodes) and
[Variables](/skills/stringvariables) are compatible with the action
message bar. Some targeters might not work properly with this mechanic.
If you happen to find a targeter that doesn't work, please be sure to
post it in the bugs/suggestion-subforum!

Note: Versions 2.3.0 onwards- The @trigger targeter is buggy for
~onAttack and ~onDamaged. Don't report it as a bug, we know.

Attributes
----------

| Attribute | Aliases | Description                                        | Default |
|-----------|---------|----------------------------------------------------|---------|
| message   | m       | The message to send. Must be surrounded by quotes. |         |

Examples
--------

    Skills:
    - actionmessage{m="<mob.name>&f is casting a spell!"} @PlayersInRadius{r=30}
    - actionmessage{m="&lHello! &cI'm &athe &9&lactionmessage-bar&r! &e:)"} @trigger ~onInteract
