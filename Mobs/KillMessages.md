
Kill Messages allow you to customize what is displayed when a player is killed by your mobs. Normally when someone is killed, it will just print “Player was slain by Zombie” or “Player burned to death”, etc. Giving your mobs custom kill messages with MythicMobs is easy and can add new depth to… dying.

Syntax
------

The syntax for adding Kill Messages is simple. You can even have multiple messages defined for each mob (a random one is then chosen).

    Souleater:
      Type: SKELETON
      Display: 'Soul Eater'
      Health: 666
      KillMessages:
      - '<target.name> had their soul completely devoured'
      - '<target.name><&sq>s soul was feasted upon by Soul Eater'
      Skills:
      ...

It's that easy! Any player killed by the Soul Eater mob would have one of those two custom death messages displayed to the server. [Variables](/Skills/Placeholders) can also be used in the message, the important one being <target.name> for the name of the dead player.

For more customization, you can also edit your config.yml file and change KillMessagePrefix. This allows you to put a simple prefix in front of all kill messages (variables do not work in the prefix, however).


### Tricks

You can use a solely empty line on the KillMessages field to deactive the mob's kill messages completely. Goes like this:

    SilentUndead:
      Type: zombie
      Display: 'Silent Undead'
      KillMessages:
      - ''