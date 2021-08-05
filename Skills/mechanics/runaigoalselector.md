Mechanic: RunAIGoalSelector
===========================

Change pathfindergoals. It is not possible to use every goal on every
entity. To change the ai of an entity, you need to use clear first.
After that you can use the runaigoalselector and add the goals you need.
Unlike the mob configuration, if you use the runaigoalselector skill,
you can only use one pathfindergoal in the mechanic. But aslong as you
dont use clear, the pathfindergoal is added to the end of the already
existing goals of the entity.

A list of AI Goals can be found
[here](http://mythicmobs.net/manual/doku.php/databases/mobs/aigoals#creatures_only)

Possible Pathfindergoals
------------------------

-   clear or reset (clear all goals of the entity)
-   arrowattack
-   skeletonbowattack / bowshoot / bowmaster
-   breakdoor
-   eatgrass
-   fleegolems / runfromgolems
-   fleeplayers / runfromplayers
-   fleevillagers runfromvillagers
-   fleesun
-   float / swim
-   gotolocation / goto (parse the specialchars!) Look here:
    [Variables](/skills/stringvariables)
-   gotoowner
-   lookatplayers
-   leapattarget
-   meleeattack
-   spiderattack
-   moveindoors
-   movethroughvillage
-   movetowardsrestriction
-   movetowardstarget
-   opendoor
-   opendoors
-   patrol / patrolroute (parse the special chars!) Look here:
    [Variables](/skills/stringvariables)
-   randomlookaround / lookaround
-   randomstroll
-   restrictopendoor
-   closedoors
-   restrictsun

Example
-------

Skill.yml:

    ChangePatchfinderGoalExample:
      Skills:
      - runaigoalselector{goal=clear}
      - runaigoalselector{goal=fleesun}
      - runaigoalselector{goal=randomstroll}
