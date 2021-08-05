Mechanic: RemoveTag
===================

Removes a scoreboard tag from the target.

This is used in conjunction with the **hastag condition** (see
[Conditions](/conditions/start)). You can also use the vanilla command
"/scoreboard players tag &lt;player name&gt; remove [Tag Name] " to do
the same thing.

Attributes
----------

| Attribute | Aliases | Description                | Default Value |
|-----------|---------|----------------------------|---------------|
| tag       | t       | The string-name of the tag | default       |

  

Examples
--------

This skill would give the casting mob the tag "Test".

    TagSkill
      Skills:
      - removetag{t=Test} @self

This skill would only run on the mob if it had the tag, "Test".

    TagTest:
      Conditions:
      - hastag{t=Test}
     Skills:
      - suicide @self
