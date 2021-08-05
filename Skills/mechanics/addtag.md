Mechanic: AddTag
================

Adds a scoreboard tag to the target.

Attributes
----------

| Attribute | Aliases | Description                | Default Value |
|-----------|---------|----------------------------|---------------|
| tag       | t       | The string-name of the tag | default       |

  

Special Notes
-------------

This is used in conjunction with the **hastag condition** (see
[Conditions](/conditions/start)). You can also use the vanilla command
"/scoreboard players tag &lt;player name&gt; add [Tag Name] " to do
the same thing.

Examples
--------

This skill would give the casting mob the tag "Test".

    TagSkill
      Skills:
      - addtag{t=Test} @self

This skill would only run on the mob if it had the tag, "Test".

    TagTest:
      Conditions:
      - hastag{t=Test}
     Skills:
      - suicide @self
