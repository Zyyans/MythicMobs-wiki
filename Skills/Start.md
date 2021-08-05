Skills
======

<img src="http://fs5.directupload.net/images/160306/wf38wosn.jpg" width="500" height="250" alt="http://fs5.directupload.net/images/160306/wf38wosn.jpg" />

Skills are an integral feature of MythicMobs. All mobs (or items, if you
have the [Artifacts] add-on) are able to have skills of various types
that can be triggered under different circumstances with varying
conditions. MythicMob's skill system is simple once you get used to it
and highly flexible, and can even be used to recreate bosses from the
most popular MMORPGs in Minecraft.

Skill group(including many mechaines) must be stored in any document  
which ends in document common format(.txt .yml etc) in **Skills** Folder

Skills are made up of several distinct parts:

-   [Mechanics]
-   [Effects]
-   [Targeters]
-   [Triggers]
-   [Conditions]

Getting Started
===============

So what makes a skill?

Skills are made up of [skill mechanics][Mechanics], or "base skills",
which are simple basic skills by themselves that come with MythicMobs.
Each skill mechanic is called in the **Skills** section of a mob. Lets
take a look at an example of what this looks like:

    FieryZombie:
      Type: ZOMBIE
      Display: 'Fiery Zombie'
      Health: 50
      Skills:
      - mechanic 1
      - skill{skill=Skill group name}
      - skill{s=Skill group name}
      - skill:Skill group name}
      - etc

Each skill mechanic is assigned to the mob in a list such as the one
above. But what would a real mechanic look like? Here's a real example:

    FieryZombie:
      Type: ZOMBIE
      Display: 'Fiery Zombie'
      Health: 50
      Skills:
      - ignite{ticks=100} @target ~onAttack <50% 0.5

Yikes! What does all of that mean? Lets take a look at what makes up
this skill:

    Skills:
    - mechanic{option=value} @[targeter] ~on[trigger] [health_modifier] [chance]

This may still look pretty intimidating, but each part by itself is very
simple, and some are even optional. Lets break each part down
separately!

Mechanics
---------

The first, and most important part of a skill, is the mechanic. This is
what you want to happen, it is the base skill you are performing. It may
be dealing damage, or setting something on fire, or striking
lightning... [there are many different mechanics][Mechanics] you can
use. There are two main types of mechanics: mechanics that target
entities, and mechanics that target a location. Some can target both, or
neither.

Most mechanics also have options. These come directly after the mechanic
name and are surrounded in curly-braces {}. Each option is separated by
a semi-colon (;).

    Skills:
    - mechanic{option=value;option=value;option=value}

You can also expand the syntax to be more readable if you prefer, but
keeping the correct indentation is very important or YAML will be upset.

    Skills:
    - mechanic{
        option=value;
        option=value;
        option=value;
        }

Setting up a mechanic is as simple as identifying the mechanic you want
to use and plugging in the options you want. Most options have a default
value and are optional. So if you wanted to set someone on fire for 5
seconds, you'd use the ignite mechanic and set the "ticks" option to 100
(there are 20 ticks in a second),

    Skills:
    - ignite{ticks=100}

Targeters
---------

Targeters are another core part of implementing skills. Targeters are
"what you want the skill to hit". There are many types of targeters, and
most can be categorized into targeting "Entities" or "Locations". It is
important to choose the right targeter for what you want to do. [Here is
a list of all the targeters].

Targeters go directly after the mechanic in your skill line, and are
always prefixed with an @ symbol. Some can also have their own options,
which also go in curley braces after the targeter.

    Skills:
    - mechanic{option=value} @targeter{options=value}

Going back to our previous example, lets say you want it to set the
mob's target on fire. You'd simply do this...

    Skills:
    - ignite{ticks=100} @target

Or perhaps you want it to set ALL players nearby on fire. Lets say
within a 5 yard radius...

    Skills:
    - ignite{ticks=100} @PlayersInRadius{r=5}

Just remember, the targeter is just what you want to target.

Triggers
--------

Triggers are also a very important part of skills. Triggers determine
"what causes this skill to happen".

Triggers also interact with a specific targeter, **@trigger**, which
works with certain targeters that are triggered by other entities.

Triggers go directly after the targeter, and generally start with
**~on** and the trigger name.

    Skills:
    - mechanic{option=value} @targeter{options=value} ~onTrigger

Going back to our previous example, lets say you want this trigger to
fire when the mob attacks its target, so its melee attacks apply fire
also.

    Skills:
    - ignite{ticks=100} @target ~onAttack

**Note: Items have a different set of Triggers. [Click here to see which
triggers work with Artifacts].**

Health Modifiers
----------------

Health modifiers are a special type of condition that come after the
trigger. These allow you to easily set ranges at which skills will only
execute, and are entirely optional. Health modifiers come in several
simple forms. Here are some examples:

-   **=90%** - Mob will trigger the skill once after hitting 90% health
-   **&lt;50%** - Mob will only trigger the skill below 50% health
-   **=30%-50%** - Mob will only trigger the skill between 30% and 50%
    health
-   **&lt;2000** - Mob will only trigger the skill below 2000 HP
-   **&gt;500** - Mob will only trigger the skill above 500 HP

Health Modifiers go directly after the trigger and are prefixed with
either **=**, **&lt;**, or **&gt;**, depending on the range you want to
use.

    Skills:
    - mechanic{option=value} @targeter{options=value} ~onTrigger =HealthModifier

Going back to our previous example, lets say you want the skill to only
work when the mob is below 50% health:

    Skills:
    - ignite{ticks=100} @target ~onAttack <50%

Chance
------

Chance is another simple and optional conditional you can add onto skill
lines. Chance is always the last thing you put on the skill line, and is
a simple decimal number where 1.0 is 100%, 0.5 is 50%, and 0 is 0%.

So to wrap up the example, lets say you want this trigger to only fire
on 50% of melee attacks:

    Skills:
    - ignite{ticks=100} @target ~onAttack <50% 0.5

Wrapping it all Up
==================

As you can see, while the original skill looked intimidating, breaking
it down into pieces makes things much simpler.

Once you get the hang of using individual base-skills, you can use
Meta-Skills to combine them into more complex skills. This will be
covered in a later article.

  [Artifacts]: /Artifacts
  [Mechanics]: /Skills/Mechanics/
  [Effects]: /Skills/Effects/
  [Targeters]: /Skills/Targeters/
  [Triggers]: /Skills/Triggers/
  [Conditions]: /Conditions/
  [Here is a list of all the targeters]: /Skills/Targeters/
  [Click here to see which triggers work with Artifacts]: /Artifacts/Triggers