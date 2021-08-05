Skill Mechanics
===============

Skill Mechanics (or base skills) are simple skills that are built into
MythicMobs. You can call these basic skills by themselves in your mob's
Skill List, or you can create your own skill by combining these
mechanics.

Some Mechanics are able to target Entities, Locations, or both! Some
don't target anything. You control what your skill targets using a
[Targeter][].

Learn about the new Skill Parameter system added in MM 4.12 [here!][]

Mechanics
---------

These skills usually target entities (players or other mobs), but some
are able to target locations as well.

| Mechanic               | Description                                                    |
|------------------------|----------------------------------------------------------------|
| [Activate Spawner][]   | Activates a MythicMobs spawner at the targeted location        |
| [Animate ArmorStand][] | Animates an armorstand                                         |
| [Arrow Volley][]       | Fires a volley of arrows                                       |
| [AuraRemove][]         | Removes an aura from the target entity                         |
| [BarCreate][]          | Creates a custom boss bar on the casting mob                   |
| [BarSet][]             | Modifies a custom boss bar on the casting mob                  |
| [BarRemove][]          | Removes a custom boss bar on the casting mob                   |
| [BreakBlock][]         | Breaks the block at the target location                        |
| [BreakBlockAndGiveItem][] | Breaks the block at the target location and gives item/droptables |
| [Close Inventory][]    | Closes the target player's inventory                           |
| [Command][]            | Executes a command for each target                             |
| [Consume][]            | Deals damage and restores health per target hit                |
| [Disengage][]          | Causes the caster to leap backwards away from the target entity                               |
| [Disguise][]           | Changes the caster's disguise                                  |
| [DisguiseTarget][]     | Changes the target's disguise                                  |
| [Undisguise][]         | Remove the caster's disguise                                   |
| [Dismount][]           | Makes the caster dismount whatever they're riding              |
| [ClearThreat][]        | Makes a mob clear its threat table                             |
| [Currency Give][]      | Give money to a player. Requires Vault and a currency plugin   |
| [Currency Take][]      | Take money from a player. Requires Vault and a currency plugin |
| [Damage][]             | Damages the target for an amount                               |
| [BaseDamage][]         | Damages the target for a percent of the mob's damage stat      |
| [Percent Damage][]     | Damages the target for a percent of their health               |
| [Decapitate][]         | Drops a player head item based on target                       |
| [Doppleganger][]       | Copies the appearance of the target player                     |
| [DropItem][]           | Drops an item or droptable at the target location              |
| [Eject Passenger][]    | Ejects anything riding the caster                              |
| [Equip][]                | Causes the casting mob to equip an item                                     |
| [Explosion][]            | Causes an explosion                                                         |
| [Extinguish][]           | removes fire ticks from the target entity                                   |
| [fawePaste][]            | Pastes a Schematic using FAWE                                               |
| [Feed][]                 | Feeds the target player                                                     |
| [FillChest][]            | Fills a chest with items, or a droptable                                    |
| [Fly][]                  | Applies an [aura][] that allows the target to fly                           |
| [Force Pull][]           | Teleports the target to the mob                                             |
| [Glow][]                 | Makes the target glow                                                       |
| [Give Item][]            | Gives an item to the target                                                 |
| [Give Item From Target][] | Gives an item to the caster from the target                                |
| [Heal][]                 | Heals the target                                                            |
| [HealPercent][]          | Heals the target for a percentage of its max-health                         |
| [Ignite][]               | Sets the target on fire                                                     |
| [JSON Message][]         | Sends a JSON-format message to the target player(s)                         |
| [Jump][]                 | Causes the caster to jump                                                   |
| [Leap][]                 | Causes the caster to leap towards the target                                |
| [Lightning][]            | Strikes lightning at the target                                             |
| [Look][]                 | Causes the caster to look at the target                                     |
| [Lunge][]                | Causes the caster to lunge forward at the target                            |
| [Message][]              | Sends a message to the target player(s)                                     |
| [Modify Global Score][]  | Modifies a global scoreboard value                                          |
| [Modify Target Score][]  | Modifies a scoreboard value of the target                                   |
| [Modify Score][]         | Modifies the score of a dummy player                                        |
| [Mount][]                | Summons a mob for the caster and mounts it                                  |
| [Mount Me][]             | Forces the target entity to mount the caster                                |
| [Mount Target][]         | Mounts the target                                                           |
| [Oxygen][]               | Gives oxygen to a player target                                             |
| [PoseArmorStand][]       | Changes the pose of the target ArmorStand                                   |
| [Potion][]               | Applies a potion effect to the target                                       |
| [PotionClear][]          | Removes all potion effects from target entity                               |
| [Prison][]               | Imprisons the target inside a block                                         |
| [Pull][]                 | Pulls the target towards the mob                                            |
| [PushButton][]           | Pushes a button at the target location                                      |
| [RayTrace][]             | Traces a straight line to the target                                        |
| [RayTraceTo][]           | Executes a skill with the result of a raytrace to the target location       |
| [Rally][]                | Causes other nearby mobs to attack the target                               |
| [Random Message][]       | Sends a random message to the target player                                 |
| [Remount][]              | Remounts the mob the caster originally spawned riding, if it is still alive |
| [Remove][]               | Removes the target mob                                                      |
| [RemoveHeldItem][]       | Removes some of the item the target player is holding                       |
| [RemoveOwner][]          | Removes the ownership of the target mob                                     |
| [Run AI Goal Selector][] | Change PathfinderAIGoals                                                    |
| [Run AI Target Selector][] | Change PathfinderTargetGoals                                                       |
| [Send Action Message][]    | Sends an Actionbar Message to the target player                                    |
| [Send Resource Pack][]     | Sends a Resource Pack to the target player                                         |
| [Send Title Message][]     | Sends a Title/Subtitle Message to the target player                                |
| [Send Toast][]             | Sends an achievement toast to the target player                                    |
| [Set AI][]                 | Disables/enables the AI of the target mob                                          |
| [Set Block Type][]         | Change block type at target location                                               |
| [Set Game Mode][]          | Sets the Game Mode of the target player                                            |
| [Set Gliding][]            | Makes the target glide if they have elytra                                         |
| [Set Global Score][]       | Sets a global scoreboard value                                                     |
| [Set Gravity][]            | Sets whether gravity affects the target entity                                     |
| [Set Health][]             | Sets the health of the target entity                                               |
| [Set Level][]              | Changes the casting mob's level                                                    |
| [Set Max Health][]         | Sets the max health of the target entity                                           |
| [Set Mob Color][]          | Changes the color of the target if it is a colorable mob                           |
| [Set Mob Score][]          | Sets a scoreboard value on the casting mob                                         |
| [Set Name][]               | Changes the target entity's name                                                   |
| [Set NoDamageTicks][]      | sets the nodamageticks of the target |
| [Set Owner][]              | Makes the target the owner of the casting mob                                      |
| [Set Rotation][]           | Sets the rotation of the target                                                    |
| [Set Target Score][]       | Sets the score of the target                                                       |
| [Set Score][]              | Sets the scoreboard value of a dummy player                                        |
| [Set Speed][]              | Sets the target entity's speed attribute                                           |
| [Set Stance][]             | Sets the stance of the target mob                                                  |
| [Shield][]                 | Applies an absorb shield to the target entity                                      |
| [ShieldPercent][]          | Applies an absorb shield to the target entity for a percentage of their max health |
| [Shoot Fireball][]         | Shoots a fireball at the target                                                    |
| [Shoot Potion][]           | Throws a potion at the target                                                      |
| [Shoot Skull][]            | Shoots a wither skull at the target                                                |
| [Shoot Shulker Bullet][]   | Shoots a shulker bullet at the target entity                              |
| [Signal][]                 | Sends a signal to a mob                                                            |
| [Speak][]                  | Causes the mob to speak in chat, with options for speech bubbles                   |
| [Spring][]                 | Creates a temporary spring of liquid at the target                                 |
| [Stun][]                   | Stuns the target entity                                                            |
| [Suicide][]      | Causes the caster to die                      |
| [Summon][]       | Summons other mobs at the target              |
| [Swap][]         | Swaps locations with the target               |
| [Add Tag][]      | Adds a scoreboard tag to the target           |
| [Remove Tag][]   | Removes a scoreboard tag from the target      |
| [Teleport][]     | Teleports to the target                       |
| [TeleportIn][]   | Teleports the target relative to the caster's yaw |
| [TeleportTo][]   | Teleports the target to a specified location  |
| [Threat][]       | Modifies the mob's threat towards the target  |
| [Throw][]        | Throws the target entity                      |
| [Toggle Lever][] | Toggles a lever at the target location        |
| [Toggle Sitting][] | Toggles the sitting state for cats, dogs, foxes, and parrots |
| [Velocity][]     | Modifies the velocity of the target entity(s) |
| [Weather][]      | Modifies the weather in the target world      |
| [WolfSit][]      | Modifies the target wolves position           |

Effect Mechanics
----------------

Effects are mechanics that add special effects to your skills. They have
their own page!

[View the list of Effect Mechanics by clicking here][]

Advanced/Meta Mechanics
-----------------------

These skill mechanics have special advanced functions, and most are used
to call other skills. If you specify a target, all other skills called
by these will "inherit" the targets (if applicable).

| Mechanic            | Description                                                                             |
|---------------------|-----------------------------------------------------------------------------------------|
| **[Skill][]**       | Executes a meta-skill. The butter for your bread.                                       |
| [Aura][]            | Used to create custom status effects (buffs/debuffs) that can be targeted onto entities |
| [CancelEvent][]     | Cancel the Event that triggered the current skill-tree                                  |
| [Cast][]            | "Casts" a meta-skill using various advanced options                                     |
| [Chain][]           | Chains a skill between multiple targets that are near each other.                       |
| [ChainMissile][]    | A missile that chains between entities. **Premium-Only** mechanic!                |
| [Delay][]           | Delays execution of the current skill list                                              |
| [Global Cooldown][] | Sets the caster's Global Cooldown timer                                                 |
| [Missile][]         | Fires a homing missile projectile                                                       |
| [Modify Projectile][] | Modifying the projectile / missile / orbital                                   |
| [onAttack][]        | Applies an [aura][] to the target that triggers skills when they attack                 |
| [onDamaged][]       | Applies an [aura][] to the target that triggers skills when they take damage            |
| [onShoot][]         | Applies an [aura][] to the target that triggers skills when they shoot a bow            |
| [Orbital][]         | Applies an [aura][] that causes a projectile to orbit around the target                 |
| [Projectile][]      | Fires a highly-customizable projectile towards the target                               |
| [Shoot][]           | Shoots a projectile-item at the target                                                  |
| [Volley][]            | Shoots a volley of projectile-items at the target with various options |
| [SudoSkill][]         | Makes the target execute a skill                                       |
| [Random Skill][]      | Executes a random skill from a list                                    |
| [Totem][]             | Creates a static "totem" at a location that pulses other skills        |
| [Variable Add][]      | Adds an amount to a numeric variable                                   |
| [Variable Math][]     | Performs math on a numeric variable                                    |
| [Set Variable][]      | Sets the value of a variable                                           |
| [Variable Unset][]    | Unsets the variable                                                    |
| [Variable Subtract][] | Subtracts an amount from a numeric variable                            |

Universal Attributes
--------------------

The following attributes are applicable to all mechanics.

| Attribute      | Shorthand | Description                                    | Default |
|----------------|-----------|------------------------------------------------|---------|
| cooldown       | cd        | In seconds                                     | 0       |
| delay          |           | Delays the execution of the mechanic           | 0       |
| repeat         |           | How many times the mechanic should be repeated | 0       |
| repeatInterval |           | How many ticks must elapse between repetitions | 0       |

Upcoming Mechanics
------------------

These mechanics are currently being worked on and will be in future
releases of the plugin. Some mechanics listed here are already included,
but not yet ready for use.

| Mechanic           | Description                     |
|--------------------|---------------------------------|
| [Time][]           | Changes the time                |


  [here!]: /skills/skillparametersystem
  [Targeter]: /skills/targeters/
  [Activate Spawner]: /skills/mechanics/activatespawner
  [Animate ArmorStand]: /skills/mechanics/animatearmorstand
  [Arrow Volley]: /skills/mechanics/arrowvolley
  [AuraRemove]: /skills/mechanics/auraremove
  [BarCreate]: /skills/mechanics/barcreate
  [BarSet]: /skills/mechanics/barset
  [BarRemove]: /skills/mechanics/barremove
  [BreakBlock]: /skills/mechanics/breakblock
  [BreakBlockAndGiveItem]: /skills/mechanics/breakBlockAndGiveItem
  [Close Inventory]: /skills/mechanics/closeinventory
  [Command]: /skills/mechanics/command
  [Consume]: /skills/mechanics/consume
  [Disengage]: /skills/mechanics/disengage
  [Disguise]: /skills/mechanics/disguise
  [DisguiseTarget]: /skills/mechanics/disguisetarget
  [Undisguise]: /skills/mechanics/undisguise
  [Dismount]: /skills/mechanics/dismount
  [ClearThreat]: /skills/mechanics/clearthreat
  [Currency Give]: /skills/mechanics/currencygive
  [Currency Take]: /skills/mechanics/currencytake
  [Damage]: /skills/mechanics/damage
  [BaseDamage]: /skills/mechanics/basedamage
  [Percent Damage]: /skills/mechanics/percentdamage
  [Decapitate]: /skills/mechanics/decapitate
  [Doppleganger]: /skills/mechanics/doppleganger
  [DropItem]: /skills/mechanics/dropitem
  [Eject Passenger]: /skills/mechanics/ejectpassenger
  [Equip]: /skills/mechanics/equip
  [Explosion]: /skills/mechanics/explosion
  [Extinguish]: /skills/mechanics/extinguish
  [fawePaste]: /fawePaste
  [Feed]: /skills/mechanics/feed
  [FillChest]: /skills/mechanics/fillChest
  [Fly]: /skills/mechanics/fly
  [aura]: /skills/mechanics/aura
  [Force Pull]: /skills/mechanics/forcepull
  [Glow]: /skills/mechanics/glow
  [Give Item]: /skills/mechanics/giveitem
  [Give Item From Target]: /skills/mechanics/giveitemfromtarget
  [Heal]: /skills/mechanics/heal
  [HealPercent]: /skills/mechanics/healpercent
  [Ignite]: /skills/mechanics/ignite
  [JSON Message]: /skills/mechanics/jsonmessage
  [Jump]: /skills/mechanics/jump
  [Leap]: /skills/mechanics/leap
  [Lightning]: /skills/mechanics/lightning
  [Look]: /skills/mechanics/look
  [Lunge]: /skills/mechanics/lunge
  [Message]: /skills/mechanics/message
  [Modify Global Score]: /skills/mechanics/modifyglobalscore
  [Modify Target Score]: /skills/mechanics/modifytargetscore
  [Modify Score]: /skills/mechanics/modifyscore
  [Mount]: /skills/mechanics/mount
  [Mount Me]: /skills/mechanics/mountme
  [Mount Target]: /skills/mechanics/mounttarget
  [Oxygen]: /skills/mechanics/oxygen
  [PoseArmorStand]: /skills/mechanics/posearmorstand
  [Potion]: /skills/mechanics/potion
  [PotionClear]: /skills/mechanics/potionclear
  [Prison]: /skills/mechanics/prison
  [Pull]: /skills/mechanics/pull
  [PushButton]: /skills/mechanics/pushbutton
  [Rally]: /skills/mechanics/rally
  [Random Message]: /skills/mechanics/randommessage
  [Raytrace]: /skills/mechanics/raytrace
  [RayTraceTo]: /skills/mechanics/raytraceto
  [Remount]: /skills/mechanics/remount
  [Remove]: /skills/mechanics/remove
  [RemoveHeldItem]: /skills/mechanics/removehelditem
  [RemoveOwner]: /skills/mechanics/removeowner
  [Run AI Goal Selector]: /skills/mechanics/runaigoalselector
  [Run AI Target Selector]: /skills/mechanics/runaitargetselector
  [Send Action Message]: /skills/mechanics/sendactionmessage
  [Send Resource Pack]: /skills/mechanics/sendresourcepack
  [Send Title Message]: /skills/mechanics/sendtitlemessage
  [Send Toast]: /skills/mechanics/sendtoast
  [Set AI]: /skills/mechanics/setai
  [Set Block Type]: /skills/mechanics/setblocktype
  [Set Game Mode]: /skills/mechanics/setgamemode
  [Set Gliding]: /skills/mechanics/setgliding
  [Set Global Score]: /skills/mechanics/setglobalscore
  [Set Gravity]: /skills/mechanics/setgravity
  [Set Health]: /skills/mechanics/sethealth
  [Set Level]: /skills/mechanics/setlevel
  [Set Max Health]: /skills/mechanics/setmaxhealth
  [Set Mob Color]: /skills/mechanics/setmobcolor
  [Set Mob Score]: /skills/mechanics/setmobscore
  [Set Name]: /skills/mechanics/setname
  [Set NoDamageTicks]: /skills/mechanics/setnodamageticks
  [Set Owner]: /skills/mechanics/setowner
  [Set Rotation]: /skills/mechanics/setrotation
  [Set Target Score]: /skills/mechanics/settargetscore
  [Set Score]: /skills/mechanics/setscore
  [Set Speed]: /skills/mechanics/setspeed
  [Set Stance]: /skills/mechanics/setstance
  [Shield]: /skills/mechanics/shield
  [ShieldPercent]: /skills/mechanics/shieldpercent
  [Shoot Fireball]: /skills/mechanics/shootfireball
  [Shoot Potion]: /skills/mechanics/shootpotion
  [Shoot Skull]: /skills/mechanics/shootskull
  [Shoot Shulker Bullet]: /skills/mechanics/shootshulkerbullet
  [Signal]: /skills/mechanics/signal
  [Speak]: /skills/mechanics/speak
  [Spring]: /skills/mechanics/spring
  [Stun]: /skills/mechanics/stun
  [Suicide]: /skills/mechanics/suicide
  [Summon]: /skills/mechanics/summon
  [Add Tag]: /skills/mechanics/addtag
  [Remove Tag]: /skills/mechanics/removetag
  [Teleport]: /skills/mechanics/teleport
  [TeleportIn]: /skills/mechanics/teleportin
  [TeleportTo]: /skills/mechanics/teleportto
  [Threat]: /skills/mechanics/threat
  [Throw]: /skills/mechanics/throw
  [Toggle Lever]: /skills/mechanics/togglelever
  [Toggle Sitting]: /skills/mechanics/togglesitting
  [Velocity]: /skills/mechanics/velocity
  [Weather]: /skills/mechanics/weather
  [WolfSit]: /skills/mechanics/wolfsit
  [View the list of Effect Mechanics by clicking here]: /skills/effects/
  [Skill]: /skills/mechanics/skill
  [Aura]: /skills/mechanics/aura
  [CancelEvent]: /skills/mechanics/cancelevent
  [Cast]: /skills/mechanics/cast
  [Chain]: /skills/mechanics/chain
  [ChainMissile]: /skills/mechanics/chainmissile
  [Delay]: /skills/mechanics/delay
  [Global Cooldown]: /skills/mechanics/globalcooldown
  [Missile]: /skills/mechanics/missile
  [Modify Projectile]: /skills/mechanics/modifyprojectile
  [onAttack]: /skills/mechanics/onattack
  [onDamaged]: /skills/mechanics/ondamaged
  [onShoot]: /skills/mechanics/onshoot
  [Orbital]: /skills/mechanics/orbital
  [Projectile]: /skills/mechanics/projectile
  [Shoot]: /skills/mechanics/shoot
  [Volley]: /skills/mechanics/volley
  [SudoSkill]: /skills/mechanics/sudoskill
  [Random Skill]: /skills/mechanics/randomskill
  [Totem]: /skills/mechanics/totem
  [Variable Add]: /skills/mechanics/variableadd
  [Variable Math]: /skills/mechanics/variablemath
  [Set Variable]: /skills/mechanics/setvariable
  [Variable Unset]: /skills/mechanics/variableunset
  [Variable Subtract]: /skills/mechanics/variablesubtract
  [Swap]: /skills/mechanics/swap
  [Time]: /skills/mechanics/time