Mechanic: Speak
===============

Makes the caster speak using chat and speech bubbles. Supports
Holograms.

**Added in 4.10**

* Now allow hex colors in the format **`<#FFFFFF>`**
* Now supports gradients in the format **`<gradient:#color1:#color2>text</gradient>`**
* Now supports **`<rainbow>text</rainbow>`**
* Now supports hover text in the format **`<hover:show_text:'hover text??'>hover over me!</hover>`**
* Now supports clickable text in the format **`<click:run_command:/say hello>click me!</click>`**

Attributes
----------

| Attribute     | Aliases     | Description                                                   | Default Value                    |
|---------------|-------------|---------------------------------------------------------------|----------------------------------|
| offset        | o           | The y offset for the hologram.                                | 0.6f                             |
| radius        | r           | The radius of entities which will see the chat message .      | 12                               |
| maxlinelength | ll, mll, ml | The maximum length of the hologram.                           | 22                               |
| lineprefix    | lp          | The prefix for the hologram.                                  | &f                               |
| message       | m           | The message to be displayed (affects both hologram and chat). | NONE                             |
| chatprefix    | cp          | The prefix for the chat message.                              | &lt;caster.name&gt;&f&lt;&co&gt; |
| duration      | d, t        | The amount of time the hologram will be displayed for.        | MESSAGE LENGTH * 4              |

  

Examples
--------

      Skills:
      - speak{offset=0.6f;radius=30;maxlinelength=22;lineprefix="&5";message=" I just spawned!";chatprefix=<caster.name>&f<&co>;duration=200} @self ~onSpawn
      - ...
