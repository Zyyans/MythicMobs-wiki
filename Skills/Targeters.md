Targeters
=========

Targeters are used to determine what a skill targets when it is fired.

Targeters are always required (or the mob won't know what it is
attacking), and forgetting a targeter is probably one of the most common
mistakes people new to MythicMobs make.

If a targeter is used with a meta skill, then all of the skills inside
of the meta skill inherit the parent targeter. It is important to keep
that in mind as excessive targeter use is a common cause of poor server
performance. Of course, you can overwrite the parent targeter for
individual skills inside of the meta skill by giving them their own
targeter to use, and there are even a few targeters that work
specifically off of inherited targets.

Targeters can be as complex or as simple as you want them!

Entity Targeters
----------------

### Single-Entity Targeters

| Targeter             | Shorthand | Description                                                |
|----------------------|-----------|------------------------------------------------------------|
| @Self                | @Caster   | Targets the mob itself                                     |
| @Target              | @T        | Targets the mob's target                                   |
| @Trigger             |           | Targets the entity that triggered the skill                |
| @NearestPlayer{r=#}  |           | Targets the nearest player in radius. r=5 by default       |
| @WolfOwner           |           | Targets the owner of the wolf                              |
| @Owner               |           | Targets the [owner](/skills/mechanics/setowner) of the mob |
| @Mount (MM 2.5.0+)   |           | Targets the entity that the mob is currently riding        |
| @Parent              |           | Targets the parent if mob was summoned by other mob.       |
| @Children            |           | Targets any child entities summoned by the caster.         |
| @Passenger           |           | Targets the rider of the mob.                              |
| @CasterSpawnLocation |           | Targets the location the caster spawned at.                |
| @PlayerByName{name="Ashijin"} |  | Targets a specific player by name, supports placeholders. Added in 4.12 |
| @UniqueIdentifier{u="<target.uuid>"}  | @UUID | Targets a specific entity by their UUID, supports placeholders. Added in 5.0 |
| @Vehicle             |           | Targets the Vehicle you are mounted on Added in 4.12       |

### Multi-Entity Targeters

| Targeter                             | Shorthand          | Description                                                                                              |
|--------------------------------------|--------------------|----------------------------------------------------------------------------------------------------------|
| @LivingInCone{a=90.0;r=16.0;rot=0.0} | @EIC{}             | Targets all living entities in cone with angle a and length of r with rotation rot relative to direction |
| @LivingInWorld                       | @EIW               | Targets all living entities in casters world                                                             |
| @LivingEntitiesInRadius{r=#}        |                    | Targets all entities in the given radius                                                                 |
| @PlayersInRadius{r=#}               | @PIR{r=#}         | Targets all players in the given radius                                                                  |
| @MobsInRadius{r=#;types=X,X,X}      | @MIR{r=#;t=X,X,X} | Targets all mobs of the given type in a radius                                                           |
| @EntitiesInRadius{r=#;types=X,X,X}  | @EIR{r=#;t=X,X,X} | Targets all entities in the given radius (not sure of difference to LEIR)                                |
| @PlayersInWorld                      | @World             | Targets all players in the current world.                                                                |
| @PlayersOnServer                     | @Server            | Targets all players in the server.                                                                       |
| @PlayersInRing{min=#;max=#}        |                    | Target all players within the specified "ring" of radiis's.                                              |
| @PlayersNearOrigin{r=#}             |                    | Targets players near the [origin](/skills/targeters/origin) of a meta-skill.                             |
| @MobsNearOrigin{r=#;t=X}            |                    |                                                                                                          |
| @EntitiesNearOrigin{r=#}            |                    |                                                                                                          |
| @PlayersNearTargetLocation{r=#}     | @PNTL{r=#}        | Targets all players near targetlocation. Radius=5 by default.                                            |
| @Siblings   |     | Targets the siblings of the target. |

### ThreatTable Targeters

These targeters only work if the mob has Threat Tables enabled.

| Targeter            | Shorthand | Description                                 |
|---------------------|-----------|---------------------------------------------|
| @RandomThreatTarget | @RTT      | Targets a random person on the threat table |
| @ThreatTable        | @TT       | Targets all entities on the threat table    |
| @ThreatTablePlayers |           | Targets all players on the threat table     |
| @RTTL               |           | Targets the location of a random target on the threat table |

Location Targeters
------------------

### Single-Location Targeters

| Targeter               | Shorthand | Description                                                                                                                                                                                                                                        |
|------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| @SelfLocation{y=0.0}          |           | Targets the mob's location itself with yoffset 0.0                                                                                                                                                                                                                                                                                                  |
| @Forward{f=5;y=0.0}    |           | Targets a location 5 blocks infront of entities direction with yoffset 0.0                                                                                                                                                                         |
| @TargetLocation        | @targetloc, @TL       | Targets the mob's target's location                                                                                                                                                                                                                |
| @TriggerLocation       |           | Targets the location of the entity that triggered the skill                                                                                                                                                                                        |
| @Location{c=x,y,z,yaw,pitch}     |           | The skill will target the coordinates specified. yaw and pitch were added in MM 4.11                                                                                                                                                                                                  |
| @Origin{xoffset=0;yoffset=0;zoffset=0}     |           | Targets the location of the "origin" or "source" of a meta-skill. While that is usually the casting mob, there are special cases where that is not true (such as with the Projectile Skill, where the "origin" is the location of the projectile). |
| @Spawner{s=[string]} |           | Targets the location of the specified spawner(s). The string can be the name of a spawner, or a a group of spawners (using g:groupname), and also accepts wildcards (Spawner* would target Spawner1,Spawner2,Spawner3,etc)                        |
| @ObstructingBlock    |             | Targets any block in the way of pathfinding |

### Multi-Location Targeters

| Targeter                                        | Shorthand   | Description                                                                                                                          |
|-------------------------------------------------|-------------|--------------------------------------------------------------------------------------------------------------------------------------|
| @PlayerLocationsInRadius{r=#}                  | @PLIR{r=#} | Targets all player locations in the given radius                                                                                     |
| @Ring{radius=#;points=#;yoffset=#}              |             | Target points to form a ring of locations                                                                                            |
| @Cone{angle=#;points=#;range=#;rotation=#;yoffset=#} |             | Returns the # of points target locations that comprise a cone (Note: Cone is fixed on the y-axis, and cannot be rotated up or down) |
| @EntitiesInCone{angle=#;range=#;rotation=#;} |             | Targets all entities within the cone                                                                                                 |

Special Targeters
-----------------

| Targeter | Shorthand | Description                                                      |
|----------|-----------|------------------------------------------------------------------|
| @None    |           | Provides no target. (Useful for mechanics with no target input.) |

These are meta-targeters- they can only be used inside of skills. For
example:

    Laser:
      Mobtype: creeper
      Display: 'Laser'
      Health: 12
      AITargetSelectors:
      - 0 clear
      - 1 players
      Skills:
      - skill{s=Laser} @target
    Laser:
      Skills:
      - ignite @line{r=1}

In the mobs skill, the target specified there is the end point that the
meta-targeter uses.

| Targeter                               | Shorthand                 | Description                                                                                                                                                                                                                                                                                                                                                                                   |
|----------------------------------------|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| @Line{radius=#;fromorigin=true/false} | @Line{r=#;fo=true/false} | Targets locations between the mob and the specified target                                                                                                                                                                                                                                                                                                                                    |
| @EntitiesInLine{r=#;fo=true/false}    | @EIL{r=#;fo=true/false}  | Targets any entities in a line between the target and the casting mob.                                                                                                                                                                                                                                                                                                                        |
| @LivingNearTargetLocation{radius=5}    | @LNTL{r=#}               | Targets all living entities near meta-targeter location.                                                                                                                                                                                                                                                                                                                                      |
| @PlayersNearTargetLocation{radius=5}   | @LNTL{r=#}               | Targets all players near meta-targeter location.                                                                                                                                                                                                                                                                                                                                              |
| @RLNTE{a=#;r=#;s=#;minr=#}        |                           | Targets random locations around targeted entities. (Example usage: Meteor skill. Amount would determine how many meteors there will be, radius is how wide the field of falling meteors will be, and the spacing will be how far apart they'll be spaced apart. Generally keep the radius larger than spacing, as it is untested how a smaller radius with a large spacing will do. - zDrakon |
| @FloorOfTargets     | @FOT      | Targets the blocks underneath the targets  |
| @LocationsOfTargets | @LOT       | Targets the location of the targets        |
| @BlocksInRadius{radius=#;radiusy=#;noise=#;shape=sphere/cube;onlyair=false;noair=true} |     | Targets all blocks in the radius of the inherited target |
| @BlocksNearOrigin{radius=#;radiusy=#;noise=#;shape=sphere/cube;onlyair=false;noair=true} |     | Targets all blocks in the radius of the specified target |

Targeter Options
================

Target Filters
--------------

Target Filters allow you to filter out certain targets, and make
targeters a lot more flexible.

They are used with two options (available on ANY entity-targeter):

-   ignore=X
-   target=X

For example, to make a targeter that will ignore any players or
non-hostile mobs, you'd use this:

    damage{a=20} @EntitiesInRadius{r=10;ignore=players,animals}

To make a targeter ONLY target players, you'd do something like this:

    skill{s=ASkill} @EntitiesInRadius{r=5;target=players}

Possible filters include:

-   self
-   animals *(non-hostile mobs)*
-   creative *(ignored by default)*
-   creatures *(any type of sentient entity)*
-   flyingmobs
-   monsters *(hostile mobs)*
-   NPCs *(Citizens NPCs, ignored by default)*
-   players
-   samefaction *(mobs marked with the same faction type)*
-   spectators *(ignored by default)*
-   vanilla
-   watermobs
-   More coming later...

You can also turn off specific filters by just adding the option
**targetXXXXX** replacing XXXXX with the filter name, e.g.
**targetPlayers=false** or **targetcreative=true**

Target Limits
-------------

All entity targeters also support target limits (as of v4.5). With this
you can limit how many things you target, including the order in which
they are selected.

This is done with the options:

-   limit=#
-   sort=X

Lets say you want your ability to only target the 2 nearest players
within 30 yards. To do this, you'd simply set the limit 2 to and sort by
nearest:

-   **@PlayersInRadius{r=30;limit=2;sort=NEAREST}**

Currently sort can have the following values:

-   NONE *(usually sorts by how long the entity has existed)*
-   RANDOM
-   NEAREST
-   FURTHEST
-   HIGHEST_HEALTH
-   LOWEST_HEALTH
-   HIGHEST_THREAT
-   LOWEST_THREAT