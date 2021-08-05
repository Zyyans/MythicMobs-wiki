Skill Triggers
==============

Triggers are used to determine how a skill is triggered from within the
mobs skill configuration section.

<u>**TRIGGERS CANNOT BE USED IN META-SKILLS AND SHOULD NOT BE INCLUDED
IN THEM.**</u> Triggers can only be used *to activate* the meta-skill
itself.

**Table of all available triggers:**

| Trigger               | When it fires...                                            |
|-----------------------|-------------------------------------------------------------|
| onCombat              | Default                                                     |
| onAttack              | When the mob hits something                                 |
| onDamaged             | When the mob is damaged                                     |
| onSpawn               | When the mob spawns                                         |
| onDespawn             | When the mob is despawned                                   |
| onFirstSpawn          | Triggered the first time a mob is spawned from a spawner    |
| onDeath               | When the mob dies                                           |
| onTimer:\#            | Every \# ticks (where \# is the interval in ticks)          |
| onInteract            | When the mob is right-clicked                               |
| onKillPlayer          | When the mob kills a player                                 |
| onPlayerDeath         | When a player dies for any reason                           |
| onEnterCombat         | When the mob enters combat (requires threat tables be on)   |
| onDropCombat          | When the mob leaves combat (requires threat tables be on)   |
| onChangeTarget        | When the mob changes targets (requires threat tables be on) |
| onExplode             | When the mob explodes (typically only used for creepers)    |
| onTeleport            | When the mob teleports (typically only used for endermen)   |
| onSignal              | When the mob receives a signal                              |
| onSignal:*[signal]* | When the mob receives a specific signal                     |
| onShoot               | When the mob fires a projectile                             |

**Table of all available **MythicCrucible** triggers:**

| Trigger               | When it fires...                                            |
|-----------------------|-------------------------------------------------------------|
| onBlockBreak          | When the player breaks a block                              |
| onBlockPlace          | When the player places a block                              |
| onConsume             | Triggered if the item is food or a potion that is eaten     |
| onCrouch              | When the player crouches                                    |
| onUnCrouch            | When the player stops crouching                             |
| onDamaged             | When the player is damaged                                  |
| onDeath               | When the player dies                                        |
| onEquip               | When a player equips an armor piece.                        |
| onUnEquip             | When a player unequips an armor piece.                      |
| onInteract            | When the player interacts with an entity                    |
| onBowHit              | When a player hits an entity with an arrow                  |
| onPotionSplash        | Triggered if the item is a potion that was thrown           |
| onRightClick          | When the player right-clicks                                |
| onShoot               | When the player shoots a bow                                |
| onSpawn               | When the player logs in or respawns                         |
| onSwing               | When the player left-clicks                                 |
| onTimer:\#            | Every # ticks (where # is the interval in ticks)            |
| onUse                 | When the player right-clicks while holding the item         |
| onFish                | When the player right-clicks while holding a fishing rod    |
| onFishBite            | When a fish bites the hook from a fishing rod               |
| onFishCatch           | When the fish latches onto the hook from a fishing rod      |
| onFishGrab            | When the player right-clicks while holding the fishing rod with a latched fish |
| onFishGround          | When the bobber is stuck in the ground                      |
| onFishingReel         | When the player reels in a fishing rod with no fish on the other end |
| onFishingFail         | When the player fails a fish attempt due usually due to poor timing |
| onPressQ              | When a player presses Q to drop the item. Requires ProtocolLib |
| onPressCtrlQ          | When a player presses CTRL+Q to drop the item. Requires ProtocolLib |
| onPressF              | When a player presses F to swap the item. Requires ProtocolLib |

**Mythic Crucible** is another one of our Premium Plugins which adds new triggers and allows you to create incredible custom items! You can purchase it from [here](https://mythiccraft.io/index.php?resources/crucible-create-unbelievable-mythic-items.2/)!

Using Triggers
--------------

Triggers are defined in the skill section of the mob configuration and
must use tilda (~) in front of them. In the case of the Timer, a time
in ticks is also required.

    SkeletalWizard_Fire:
      Type: WITHER_SKELETON
      Display: '&Skeletal Fire Wizard'
      Health: 50
      Damage: 0.5
      Skills:
      - ignite{ticks=100} @target ~onAttack
      - skill{s=FireShield} @trigger ~onDamaged 0.1
      - skill{s=AOEFire} ~onTimer:300

In this example the mob will also set its target on fire when
melee-attacking, will use a "FireShield" skill when taking damage, and
will use the "AOEFire" skill every 300 ticks [1].

Not using Triggers...
---------------------

Skill triggers give far more flexibility in determining exactly when a
skill should go off. It is **highly** recommended that you trigger all
your skills using advanced triggers as opposed to the old, legacy
methods.

If a skill does not have a trigger, it will default to the "~onCombat"
trigger (shown further below) which will execute when these four basic
things occur:

-   The mob takes damage
-   The mob deals damage
-   The mob spawns
-   The mob dies

<!-- -->

    SkeletalWarrior:
      Mobtype: skeleton
      Display: '&9A Skeletal Warrior'
      Health: 100
      Damage: 2
      Drops:
      - DropTable
      Skills:
      - skill{s=Bash} =10%-90%

In this instance the Bash skill is triggered when the mob deals or takes
damage when it is between 10% and 90% health.

The @trigger Targeter
---------------------

You may have noticed there is an @trigger targeter in the examples
above, and listed in the targeters section. The @trigger will target the
"cause" of the skill being set off, i.e. if a player damages a mob and
that mob uses an onDamage-triggered skill, it will target that player.
If a signal is being sent to a mob, it will target the mob that has sent
the signal, and so on.

Detailed Descriptions & Examples
--------------------------------

**~onSpawn**

-    Trigger the skill to execute when the mob spawns.
-    This will only occur once.
-    Can be used along with the chance parameters to make the chance to
    execute less than 100%
-    **- skill{s=DamageImmunity} ~onSpawn 0.50** (The mob has a 50%
    chance to use a DamageImmunity skill when it spawns)

**~onDeath**

-    Trigger the skill to execute when the mob dies.
-    This will only occur once.
-    Can be used along with the chance parameters to make the chance to
    execute less than 100%
-    **- skill{s=SpawnSpiderlings} ~onDeath 1** (The mob has a 100%
    chance to use a SpawnSpiderlings spell when it dies)

**~onAttack**

-    Trigger the skill to execute when the mob attacks.
-    This will occur anytime the mob attacks something.
-    Can be used along with the health and chance parameters to further
    define when this occurs.
-    **- skill{s=Bash} ~onAttack &lt;50% 0.1** (The mob has a 10%
    chance to use the Bash skill when it attacks and has less than 50%
    health)

**~onDamaged**

-    Trigger the skill to execute when the mob takes damage.
-    This will occur anytime the mob takes damage.
-    Can be used along with the health and chance parameters to further
    define when this occurs.
-    **- skill{s=FlameShield} ~onDamaged 1** (The mob has a 100% chance
    to use the FlameShield skill when it takes damage)

**~onExplode**

-    Trigger the skill to execute when the mob explodes.
-    This will generally occur only once unless you have the
    PreventSuicide option set. Generally only works with creepers, since
    other mobs tend to not explode...
-    Can be used along with the chance parameters to make the chance to
    execute less than 100%
-    **- skill{s=SpawnCreeper} ~onExplode 0.25** (The mob has a 25%
    chance to use the SpawnCreeper skill when it explodes)

**~onTeleport**

-    Trigger the skill to execute when the mob teleports.
-    Generally only used for Endermen or mobs that have skills that
    allow them to teleport.
-    Can be used along with the health and chance parameters to further
    define when this occurs.
-    **- skill{s=GustOfWind} ~onTeleport &lt;50% 1** (The mob has a
    100% chance to use a GustOfWind spell when it teleports if it has
    less than 50% health)

**~onTimer:&lt;ticks&gt;**

-    Trigger the skill to execute based on a timer.
-    The timer is in ticks so 20 ticks equates to 1 second.
-    Avoid using with health or chance parameters as it does not work
    well with these at the moment.
-    Care must be taken when using the Timer trigger as skills that are
    not properly designed can potentially lead to server or client side
    performance issues. Skills with particularly low timers that call
    complex syntax can cause server side performance issues, while large
    count particle effects and other graphic intensive things can lead
    to potential client side performance issues.
-    **- skill{s=SingleTargetFire} ~onTimer:200** (The mob will use the
    SingleTargetFire skill every 10 seconds)

**~onPlayerKill**

-    Trigger the skill to execute when the mob kills a player character.
-    Can be used along with the health and chance parameters to further
    define when this occurs.
-    **- skill{s=BossRegen} ~onPlayerKill &gt;0 1** (The mob has a 100%
    chance to use the BossRegen spell when it kills a player)

**~onEnterCombat**

-    Trigger the skill to execute when the mob enters combat.
-    **- skill{s=BuffSelf} ~onEnterCombat &gt;0 1** (The mob has a 100%
    chance to use the BuffSelf skill when it enters combat with a player
    or mob)

**~onDropCombat**

-    Trigger the skill to execute when the mob drops combat.
-    **- skill{s=BossRegen} ~onDropCombat &gt;0 1** (The mob has a 100%
    chance to use the BossRegen skill when it drops combat with a player
    or mob)

**~onChangeTarget**

-    Trigger the skill to execute when the mob changes target.
-    **- skill{s=Charge} ~onChangeTarget &gt;0 1** (The mob has a 100%
    chance to use the Charge skill when it changes targets)

**~onInteract**

-    Trigger the skill to execute when the player interacts with them
    (right-clicks on them).
-    **- skill{s=QuestDialogue} ~onInteract &gt;0 1** (The mob has a
    100% chance to use the QuestDialogue skill when the player interacts
    or right-click on it)

**~onSignal** or **~onSignal:[signal]**

-   Trigger for skill to execute when the mob receives a signal or when
    with :[signal] only a specific signal
-   Useful for skills that require communication between mobs or from a
    player to a mob [2], which was previously (pre 2.3) only possible by
    workarounds
-   See
    [signal-skill](http://www.mythicmobs.net/manual/doku.php/skills/mechanics/signal)
    page.

**~onShoot**

-    Trigger the skill to execute when the mob fires a projectile
    (Ghast/Blaze Fireballs).
-    **- skill{s=ExplodeParticles} ~onShoot &gt;0 1** (The mob has a
    100% chance to use the ExplodeParticles skill when it fires a
    projectile)

[1] 20 ticks = 1 second

[2] players can communicate signals to mobs by using the
mythicmobs-command /mm signal &lt;uuid&gt; &lt;signal&gt;