Mechanic: Message
=================

Sends a chat message to the target, if the target is a player. [Color
codes](/databases/misc/colorcodes) and
[variables](/skills/stringvariables) are useable in this mechanic.

**Added in 4.10**

* Now allow hex colors in the format **`<#FFFFFF>`**
* Now supports gradients in the format **`<gradient:#color1:#color2>text</gradient>`**
* Now supports **`<rainbow>text</rainbow>`**
* Now supports hover text in the format **`<hover:show_text:'hover text??'>hover over me!</hover>`**
* Now supports clickable text in the format **`<click:run_command:/say hello>click me!</click>`**

Attributes
----------

| Attribute | Aliases | Description                 | Default |
|-----------|---------|-----------------------------|---------|
| message   | msg,m   | The message to send.        | None    |
| audience  |         | the audience of the message |         |

---------------

Audience attribute was added in 4.12. possible audience options are: caster, target, and world.

Examples
--------

      Skills:
      - message{m="<mob.name>&f<&co> Hahaha! You will all die!"} @PlayersInRadius{r=30}
