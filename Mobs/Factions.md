Customizing Mob AI
==================

MythicMobs provides the ability to program custom mob AI in your mobs
which allows for a huge amount of additional customization as to how
mobs attack, what targets they choose to attack, and other actions.

In the following sections I will provide some examples on how to
configure a couple common scenarios that you may want to use on your
server.

**Note on Players:**
By default, MythicMobs uses a permission system for players to be considered part of a faction. If a player has the permission `faction.(factionname)`, they will be considered in the faction.

This behavior can be overridden using the API by registering a custom faction provider.

AI Goals, Targets, and Factions
-------------------------------

-   Custom AI generally requires two things configured in order to work.
    You need **AI Goals**, which tell the mob how it should act, and you
    need **AI Targets** which tells the mob how it should target things.
-   **Factions** are used to separate mobs into groups and will be used
    later for more advanced configurations.
-   By default, most (not all) Minecraft mobs have some sort of internal
    list of AI goals that tells them how their AI should work. As an
    example, the Skeleton AI says that it should target players and that
    it should use the arrow attack option when attacking said players.
-   In order to re-program AI using MythicMobs we must first clear its
    AI goals and targets and then add new objectives to these areas.
-   Custom AI does not work with all mobs. Some mobs, such as the
    Enderdragon, are hard-coded and cannot be changed. **Attempting to
    change the AI on these may even crash your server, so be wary and
    use test environments!**

<!-- -->

    DecayingSkeleton:
      Mobtype: skeleton
      Display: '&aa decaying skeleton'
      Health: 15
      Damage: 1
      Faction: Undead
      AIGoalSelectors:
      - clear
      - arrowattack
      AITargetSelectors:
      - clear
      - players
      Options:
        FollowRange: 10
        MovementSpeed: 0.2
        PreventOtherDrops: true

-   This example shows how the Skeleton AI generally works for
    attacking. (minus all the fluff, such as randomly walking around).

<!-- -->

        * The **AIGoalSelectors** section tells the Skeleton Mob to use the **arrowattack** action when it is going about its day to day goals.
        * The **AITargetSelectors** section tells the Skeleton Mob that it should look to target players to use the **arrowattack** action on.
        * As you see **clear** is always first, which in this case wipes the mobs AI so you have a clean slate to work with. This is important otherwise your AI may not function the way you would expect.
    * Now lets say we want the skeleton to attack other mobs instead and we want him to use a melee attack instead of a ranged attack. See below for how we accomplish this.

    DecayingSkeleton:
      Mobtype: skeleton
      Display: '&aa decaying skeleton'
      Health: 15
      Damage: 1
      Faction: Undead
      AIGoalSelectors:
      - clear
      - meleeattack
      AITargetSelectors:
      - clear
      - hurtbytarget
      - otherfactionmonsters
      Equipment:
      - COS_WoodSword:0
      Options:
        FollowRange: 10
        MovementSpeed: 0.2
        PreventOtherDrops: true

-   The skeleton AI now is programmed to attack other mobs, and any mobs
    that attack it first. In addition, it will use the melee attack
    instead of ranged attack.

<!-- -->

        * The **AIGoalSelectors** section now has the **meleeattack** goal which says to attack using melee. It should be noted that you must equip the skeleton with a sword now so he can use the melee attack since you can't melee with a bow equipped (the skeletons default weapon) This would not be required however for a zombie.
        * The **AITargetSelectors** section now has the **players** target removed so the skeleton will not actively engage players. Instead it has the **otherfactionmonsters** target, which tells it that it should attack any monsters that are not in its own faction (in this case Undead). There is also **hurtbytarget** selector with a priority of 1 which says that if any other entities attacks the skeleton first (such as a player) then it will retaliate. This target selector is a common one that should be set as a higher priority so that mobs don't end up being exploitable. Without this here, the player could kill the skeleton without it attacking back which generally is not wanted.

-   For a list of all the target and goal selectors please see [Mob AI
    Goals](Databases/Mobs/Aigoals)

<!-- -->

-   In the next two sections I will provide some examples for AI
    configuration for two common scenarios you may wish to implement on
    your server.

Example 1: Guards attack nearby monsters
----------------------------------------

-   In this scenario we want to setup some guards at the entrance to our
    city which should repel monsters that wander too close. You could
    use an Iron Golem for this function disguised as a villager, but
    their AI harder to control and they have special knock-up attacks
    that make it unfair for the mobs, so we're going to use MythicMobs'
    Custom AI to accomplish the same thing in a better way.
-   The first thing we need is a beefy guard mob to protect our town.
    Lets create a skeleton disguised as a villager, and equip him with a
    sword.

<!-- -->

    SummonedGuard1:
      Mobtype: skeleton
      Display: '&Ea town guard'
      Health: 500
      Damage: 5
      Equipment:
      - COS_StoneSword:0
      Options:
        Disguise: villager
        Despawn: true
        FollowRange: 5
        AlwaysShowName: false
        MovementSpeed: 0.35
        PreventOtherDrops: true
        KnockbackResistance: 1
        PreventMobKillDrops: true

-   So if we tie this mob to a mob spawner at our gates, he's going to
    go attack all of our players in the town so we need to make some
    adjustments to make him friendly.

<!-- -->

    SummonedGuard1:
      Mobtype: skeleton
      Display: '&Ea town guard'
      Health: 500
      Damage: 5
      Equipment:
      - COS_StoneSword:0
      Faction: Guard
      AIGoalSelectors:
      - clear
      - opendoors
      - meleeattack
      AITargetSelectors:
      - clear
      - hurtbytarget
      - otherfactionmonsters
      Options:
        Disguise: villager
        Despawn: true
        FollowRange: 5
        AlwaysShowName: false
        MovementSpeed: 0.35
        PreventOtherDrops: true
        KnockbackResistance: 1
        PreventMobKillDrops: true

-   Now the mob will target other factions containing monsters besides
    his own and will target anyone that hurts him (this will keep some
    of our less ethical players from killing our guards for the hell of
    it) He will also open any doors in his way to get to his target.
-   So this is the first half of the problem. Next we need to ensure
    that our monsters that are roaming outside our walls will attack
    back against our guards.
-   Below we will grab our Decaying Skeleton mob and configure him as
    such.

<!-- -->

    DecayingSkeleton:
      Mobtype: skeleton
      Display: '&aa decaying skeleton'
      Health: 15
      Damage: 1
      Faction: Undead
      AIGoalSelectors:
      - clear
      - meleeattack
      AITargetSelectors:
      - clear
      - hurtbytarget
      - players
      Equipment:
      - COS_RawHead:4
      - COS_WoodSword:0
      Options:
        Despawn: true
        FollowRange: 10
        AlwaysShowName: false
        MovementSpeed: 0.2
        PreventOtherDrops: true

-   Our decaying skeleton is now in the Undead faction (different then
    the Guard faction) and so he will be attacked by the guard. Also, by
    adding the **hurtbytarget** target selector, our decaying skeleton
    will now fight back if engaged with a guard (and ultimately die)
-   For any other mobs we have that spawn near the town, we would want
    to add the the same AI Goals and Targets as configured above for the
    skeleton making sure that the mob has a different faction then the
    guard.

<!-- -->

-   Now when we setup our mob spawners for our town guard at the gates,
    he will repel monsters but ignore players (as long as they leave the
    guard alone)
-   Some additional settings that we would probably want to set in this
    case are a short follow range for the guard (5 in this case) and a
    short leash range for the mob spawner. This will ensure that the
    guard doesn't go off on a rampage and kill all the monsters that we
    want our players to be able to kill for experience and loots. We
    also want to ensure that the guard has the **PreventMobKillDrops**
    set to true so that his kills don't drop exp/loot for our players.

Example 2: Orcs and Goblins attack each other
---------------------------------------------

-   So in our world we have two factions, the goblins and the orcs and
    they don't like each other much. We have a battlefield setup where
    they are at constant war except right now they are both using the
    skeleton mob type with its default AI and they aren't doing much
    fighting.
-   We want to configure them using Mythic Mobs Custom AI so that they
    fight each other when nearby in addition to any players that wander
    onto the battlefield.
-   Lets create an Orc mob and a Goblin mob.

<!-- -->

    OrcCenturion:
      Mobtype: villagezombie
      Display: '&aan orc centurion'
      Health: 50
      Damage: 4
      Faction: Orcs
      AIGoalSelectors:
      - clear
      - opendoors
      - meleeattack
      AITargetSelectors:
      - clear
      - hurtbytarget
      - specificfactionmonsters Goblin
      - players
      Equipment:
      - C_DeathfistSkullcap:4
      - C_DeathfistTunic:3
      - C_DeathfistLeggings:2
      - C_DeathfistBoots:1
      - COS_WoodSword:0
      Options:
        Despawn: true
        FollowRange: 10
        AlwaysShowName: false
        MovementSpeed: 0.25
        PreventOtherDrops: true
        PreventItemPickup: true
        KnockbackResistance: 0.25
        PreventMobKillDrops: true
        
    GoblinBattlemaster:
      Mobtype: zombie
      Display: '&aa goblin battlemaster'
      Health: 80
      Damage: 4
      Faction: Goblin
      AIGoalSelectors:
      - clear
      - opendoors
      - meleeattack
      AITargetSelectors:
      - clear
      - hurtbytarget
      - specificfactionmonsters Orcs
      - players
      Equipment:
      - COS_BronzeHead:4
      - COS_BronzeChest:3
      - COS_BronzeLegs:2
      - COS_BronzeFeet:1
      - COS_WoodAxe:0
      Skills:
      - skill BashI ~onAttack >0 0.25
      Options:
        Despawn: true
        FollowRange: 10
        AlwaysShowName: false
        MovementSpeed: 0.25
        PreventOtherDrops: true
        PreventItemPickup: true
        KnockbackResistance: 0.4    
        PreventMobKillDrops: true

-   So there are a few things we've configured here of note.

<!-- -->

        * First we have set the orc mob on the **Orc Faction** and the Goblin mob on the **Goblin Faction**. This will logically separate the two mob types.
        * Next we configure both of the mobs with the standard **clear, opendoors, and meleeattack** actions which is common for most melee type mobs.
        * Lastly we clear our AI then setup three AI target selectors. 

            * First is the **hurtbytarget** selector which as mentioned before is a good fall back option so that mobs can not be exploited by other mobs or players that they will not retaliate against.
        * Next is the **specifictargetfaction** selector with the opposing faction in it. This is set to priority 2 so the goblins and orcs will target each other first when they aren't already in combat 
            * Last is the **players** target selector which tells that mobs to attack players if there are no goblins/orcs nearby.
    * Lastly remember to set the **PreventMobKillDrops** to true so that warring npc factions don't drop exp / loots for players that happen to wander by.
    * If we have other goblin or orc mob types, we need only copy and paste these AI configurations into their mob setups and they should react similarly to the two mobs above.