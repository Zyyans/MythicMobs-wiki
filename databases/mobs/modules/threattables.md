Threat Tables
=============

<img src="http://fs5.directupload.net/images/160325/xjwfkhah.jpg" width="500" height="250" alt="http://fs5.directupload.net/images/160325/xjwfkhah.jpg" />

Threat Tables change how a mob tracks its targets. Normally Minecraft
mobs do not follow any kind of rigid system of what to target - they
will simply bounce back and forth between attacking whatever hits them.
Threat Tables change that.

With Threat Tables enabled, mobs will keep track of how much damage each
player does to them, and will attack the player that deals the most
damage. That way you can avoid scenarios where one player will hit a mob
and then run away while others follow behind smacking it forever,
trivializing it.

Threat Tables come with several built-in features to make the mob's
targeting intelligent, and use rules found in common MMORPGs. Players
gain threat by dealing damage, and will lose threat if they kite the
boss, stay outside of the boss' MaxCombatRange, or stay out of line of
sight for long periods of time. Players will also drop threat if they
leave the world or log off.

Mobs will only switch targets if another player passes 110% threat over
the current target.

Note that activated threat tables will "override" the [AI target
selectors](/databases/mobs/aigoals) you specified for the mob. A mob
with activated threat tables will attempt to attack any entity that
deals damage to it - even if such entites are not listed in the AI
target selectors or even if the AI target selector list for the mob has
been swiped clean and the mob doesn't naturally attack anything or
anyone.

Enabling Threat Tables
----------------------

Turning on Threat Tables for a mob is easy. Just add
**Modules.ThreatTable:** true to your mob, like this:

    BigScaryBoss:
      Type: zombie
      Display: '&6Zombie'
      Health: 20000
      Modules:
        ThreatTable: true

That's it!

Manipulating Threat Levels
--------------------------

If a mob has threat tables enabled, it will always target the entity
with the highest threat level on its own threat table. This process is
fully automated and based on which entity does how much damage to the
mob. Naturally, the entity (usually a player) dealing the most damage,
will gain the most threat and become the target of the mob.

However if you would like to manually make your mob target specific
entites, or just throw in some tweaks that make your mobs targeting even
smarter, you can do so using the [Threat
Mechanic](/skills/mechanics/threat).

Threat Tables also come with an API, including a "taunt" method and
threat altering methods, if another plugin author ever wanted to have
skills or abilities that interact with threat.
