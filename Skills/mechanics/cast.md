Mechanic: Cast
==============

Cast is an [Aura](/skills/mechanics/aura) mechanic similar to
[Skill](/skills/mechanics/skill) in that it executes a skill, however
Cast instead "casts" the skill similar to how you'd expect an RPG hero
or monster to do so. Cast will execute the given skill if the cast
completes successfully (e.g. if the aura finishes normally), but can be
interrupted.

Only one spell can be cast at a time, and which runs as an aura on the
caster named **#casting**. Removing the aura from the entity will
interrupt the cast. Any aura settings that cause the cast to stop early
will also interrupt casting, such as cancelling on move or teleport.

Attributes
----------

*Cast can also use most [Aura](/skills/mechanics/aura) attributes*

| Attribute     | Aliases | Description                                                          | Default |
|---------------|---------|----------------------------------------------------------------------|---------|
| onCast        | oc      | Skill to execute if the cast finishes successfully                   |         |
| onInterrupted | oi      | Skill to execute if the cast is interrupted                          |         |
| onNoTarget    | ont     | Skill to execute if no target is found                               |         |
| skillname     | sn      | Display name of the spell in the cast bar                            |         |
| showCastBar   | cb      | Whether to show the cast bar. Requires a compatible hologram plugin. | true    |
| cancelOnMove  | com     | Whether to cancel the aura if the caster moves                       | false   |

  

Examples
--------

    Skills:
    - cast{
          skillName="&aFrost Blast"
          duration=40;
          onCast=FrostBlast-Cast;
          onTick=FrostBlast-Tick;
          onInterrupted=FrostBlast-Interrupted;
          onNoTargets=FrostBlast-NoTargets;
          cancelOnMove=true;
          showCastBar=true
        } @target ~onTimer:100
