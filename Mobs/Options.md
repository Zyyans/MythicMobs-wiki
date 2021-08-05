Mob Options
===========

<img src="http://fs5.directupload.net/images/160306/36ll7s25.jpg" width="500" height="200" alt="http://fs5.directupload.net/images/160306/36ll7s25.jpg" />

This is a database of all options available when creating a mob in
MythicMobs. These options go under the Options tag like so:

    VeryFastSkeleton:
      Type: skeleton
      Display: 'Very Fast Skeleton'
      Options:
        MovementSpeed: 0.3
        NoDamageTicks: 50

### Universal options

These options are universal and will work regardless of the mobtype.

#### All mobs

**AlwaysShowName: \[true/false\]**

      * Whether the name-tag should always be displayed, even when not looking at the mob and through blocks.
      * Equivalent of the NBT-tag "CustomNameVisible"
      * MC 1.8 and earlier: armor stands only
      * MC 1.9 and later: all entites
      * Defaults to false.

**AttackSpeed: \[number\]** (2.4)

      * Sets the attack speed of the mob.
      * Defaults to vanilla attack speed for the respective mobs.

**ApplyInvisibility: \[true/false\]** (4.9)

      * Sets permanent invisibility effect on the mob (No need for invisibility potions ~onSpawn).
      * Defaults to false.

**Collidable: \[true/false\]** (2.4)

      * Whether the mob has collision.
      * Defaults to true.
      * Note that collisions in Minecraft are bidirectional, so this would need to be set to false on both the collidee and the collidant to ensure no collisions take place.

**Despawn: \[true/false\]**

      * Determines whether mobs will despawn if no players are nearby.
      * Should generally be turned on if you are using a lot of a mob spawners or entities will overwhelm your server.
      * Equivalent NBT-tag is "PersistenceRequired"
      * Defaults to true.

**FollowRange: \[value\]**

      * Max distance the mob will hold aggro on a target.
      * Also defines max range at which a target will aggro a player initially.
      * Defaults to standard respective minecraft follow range

**Glowing: \[true/false\]** (2.4)

      * Whether the mob should permanently be glowing.
      * Defaults to false.

**Invincible: \[true/false\]**

      * Makes the mob completely invincible to all types of damage.
      * //Cannot// be changed by command skills!
      * Defaults to false.

**Interactable: \[true/false\]**

      * Make the mob none interactable. In case of armor stand, denies interacts with its equipment.
      * Defaults to false.

**LockPitch: \[true/false\] (4.9)**

      * Requires protocollib, keeps mobs heads from looking up/down.
      * Defaults to false.

**KnockbackResistance: \[number\]**

      * Number between 0 and 1 that defines resistance of mob to knockbacks. Defaults to 0.
      * 0.1 = 10%, 0.5 = 50% 1 = 100%
      * Note that mobs with 100% resistance can still be knocked back by weapons enchanted with knockback or explosions.

**MaxCombatDistance: \[number\]**

      * The mob cannot be damaged by players further away than # many blocks.
      * Setting this option to a number less than the distance of a certain mob skill or attack will ensure that the mob can damage the player and will not be as easy to exploit.

**MovementSpeed: \[number\]**

      * The movement speed of the mob.
      * Most mobs default to movement speed of 0.2
      * Values above 1 tend to make the mob difficult / impossible to fight.

**NoAI: \[true/false\]** *(2.2.1)*

      * Wether or not the mob should have AI. //Will override any settings specified in AIGoalSelectors!//
      * As opposed to AIGoalSelectors, this will work on Enderdragons and Withers.
      * Defaults to false.

**NoDamageTicks:\[number\]**

      * Defines how long the mob is invulnerable after being hit.
      * If ImmunityTables are turned on for the mob, NoDamageTicks are per player as opposed to global.
      * Defaults to 10.

**NoGravity: \[true/false\]** (2.5, MC 1.10)

      * Whether the mob should not have gravity.
      * Defaults to false.
      * Note that when this is true, the mob CANNOT have the skill [[skills/mechanics/velocity|velocity]] used on it.

**PassthroughDamage: \[true/false\]**

      * Causes all damage taken to be redirected to the mob's parent, if they exist
      * Defaults to false

**Persistent: \[true/false\]**

      * Makes the mob immune to the "mm m killall" command
      * The mob can still despawn if "Despawn" is set to true
      * The mob can still be killed if targeted in the "mm m kill X" command or using a "minecraft:kill" command
      * Defaults to false

**PreventItemPickup: \[true/false\]**

      * Prevents mobs from picking up items.
      * Defaults to true.

**PreventLeashing: \[true/false\]**

      * Whether to prevents a leash from being placed on the mob.
      * Defaults to true

**PreventMobKillDrops: \[true/false\]**

      * Prevents mobs killed by that MythicMob from dropping loot.
      * Defaults to false.
      * ''As of version 2.3 and before, this option will also prevent players from dropping their inventory upon death if killed by a mob with this option turned on. Do not use in combination with gamerule keepInventory false!''
      * This is fixed in version 2.5.0

**PreventOtherDrops: \[true/false\]**

      * Should MythicMobs block the mob from dropping its normal items?
      * Defaults to false.

**PreventRandomEquipment: \[true/false\]**

      * Whether a mob should be allowed to spawn with random equipment.
      * Defaults to false.

**PreventRenaming: \[true/false\]**

      * Whether to prevent renaming using a nametag.
      * Defaults to true.

**PreventSunburn: \[true/false\]**

      * Whether to prevent the mob from burning in the sun.
      * Defaults to false.

**RepeatAllSkills: \[true/false\]**

      * Whether to repeat HP based skills if a mob heals back above the health threshold for them.
      * Defaults to false.

**ShowHealth: \[true/false\]**

      * Displays health of mob through messages broadcast within a radius defined by **show<nowiki>*</nowiki>health<nowiki>*</nowiki>radius**    and formatted according to **show<nowiki>*</nowiki>health<nowiki>*</nowiki>format**. Both of these are global settings under **config.yml**
      * Defaults to false.

**Silent: \[true/false\]**

      * Whether or not a mob should use vanilla sound effects.
      * Defaults to false.

------------------------------------------------------------------------

### Mob specific options

These are specific mob options and will have no effect when used on a
different mobtype.

#### Armor Stands

**CanMove: \[true/false\] (4.9)**

      * Whether an armor stand can move or not.
      * Only applies to armor stand type mobs.
      * Defaults to true.
      * Requires PaperSpigot

**CanTick: \[true/false\] (4.9)**

      * Whether an armor stand can tick or not.
      * Only applies to armor stand type mobs.
      * Defaults to true.
      * Requires PaperSpigot

**HasArms: \[true/false\]**

      * Whether an armor stand has arms or not.
      * Only applies to armor stand type mobs.
      * Defaults to false.
      * Broken prior to 2.5.0

**HasBasePlate: \[true/false\] (4.9)**

      * Whether an armor stand has a baseplate or not.
      * Only applies to armor stand type mobs.
      * Defaults to true.

**HasGravity: \[true/false\]**

      * Whether an armor stand is affected by gravity or not.
      * Only applies to armor stand type mobs.
      * Defaults to true.

**Invisible: \[true/false\]**

      * Whether an armor stand is invisible or not.
      * Only applies to armor stand type mobs.
      * Defaults to false.

**ItemBody: \[MythicItem Name\]**

      * Designates the Mythic Item that should go in the body/chest slot of an armor stand.
      * Only applies to armor stand type mobs.

**ItemFeet: \[MythicItem Name\]**

      * Designates the Mythic Item that should go in the feet slot of an armor stand.
      * Only applies to armor stand type mobs.

**ItemHand: \[MythicItem Name\]**

      * Designates the Mythic Item that should go in the hand slot of an armor stand.
      * Only applies to armor stand type mobs.

**ItemHead: \[MythicItem Name\]**

      * Designates the Mythic Item that should go in the head slot of an armor stand.
      * Only applies to armor stand type mobs.

**ItemLegs: \[MythicItem Name\]**

      * Designates the Mythic Item that should go in the legs slot of an armor stand.
      * Only applies to armor stand type mobs.

**Marker: \[true/false\]**

      * Whether the Armor Stand should be a marker.
      * Setting this option to true will prevent the armor stand from being destroyed in the game - making it completely non-interactable.

**Small: \[true/false\]**

      * Whether an armor stand is small or not.
      * Only applies to armor stand type mobs.
      * Defaults to false.

**Pose:** (2.4.4)

-   **Head: \[0,0,0\]**
-   **Body: \[0,0,0\]**
-   **LeftArm: \[0,0,0\]**
-   **RightArm: \[0,0,0\]**
-   **LeftLeg: \[0,0,0\]**
-   **RightLeg: \[0,0,0\]**
-   All these values default to zero.
-   All values accept number ranges - see example below.
-   Note that these pose options will not be recognized under the
    options-tag but must be set like this:
-   `Mob:
      Type: armor_stand
      Pose:
        Head: 0,50,0
        Body: 0,10,10
        LeftArm: 0 to 360,0,0
        RightArm: 0 to 90,0,0`

#### Bees

**Anger: \[number\] (4.9)**

      * Sets the time in ticks until bee anger ends.
      * If set to 0 the bee will not be angry.
      * Defaults to 0.

**HasNectar: \[true/false\] (4.9)**

      * Whether the bee is carrying pollen.
      * Defaults to false.

**HasStung: \[true/false\] (4.9)**

      * Whether the bee has stung an entity.
      * Defaults to false.

#### Chicken

**Jockey: \[true/false\]**

      * Wether or not the chicken is a chickenjockey.
      * Doesn't really do anything, but it's nice to have options.
      * Defaults to false.

#### Creepers

**ExplosionRadius: \[number\]**

      * Sets the radius/power of the creepers explosion

**FuseTicks: \[number\]**

      * Sets the number of ticks it takes for creepers to explode.

**SuperCharged: \[true/false\]**

      * Wether the creeper should spawn as a super charged creeper.
      * Defaults to false.

**PreventSuicide: \[true/false\]**

      * Prevents creepers from dying upon exploding. Set `mobGriefing` gamerule to true for this option to work.
      * Defaults to false.

#### Enderman

**PreventTeleport: \[true/false\]**

      * Meant for Enderman but //might// work on other mobs. May break teleport skills!
      * Defaults to false.

**HeldBlock: `[Material]`**

      * Sets the block that the Enderman is carrying.

#### Experience_orb

**Experience: \[Number\]**

      * Sets the amount of experience give by the experience orb mob (4.12 MM)
      * Defaults to 1

#### Falling Blocks

**Block: \[Material type\]**

      * Determines the type of the block.
      * Defaults to STONE

**BlockData: \[Number\]**

      * Additional field for inputting blockdata.
      * Defaults to 0

**DropsItem: \[true/false\]**

      * Drops the falling block's item.
      * Defaults to true

**HurtsEntities: \[true/false\]**

      * Damages entities on impact.
      * Defaults to true

#### Fox

**FoxType: \[Entity type\] (4.9)**

      * Determines the type of the fox. 
      * Can be RED or SNOW
      * Defaults to RED

#### Hoglin

**ImmuneToZombification: \[true/false\] (4.10)**

      * Whether or not the hoglin is immune to being zombified
      * Defaults to false

**Huntable: \[true/false\] (4.10)**

      * Whether the hoglin is able to be hunted by piglins.
      * Defaults to true

#### Horses, Donkeys, and Mules

**HorseArmor: \[armor\_type\]**

      * Used for horses to set the type of armor they have on.
      * Can be iron, gold, or diamond
      * [armor_type] must be in lower case

**CarryingChest: \[true/false\]**

      * Used for donkeys to set whether they are carrying a chest or not.
      * Defaults to false.

**HorseColor: \[horse\_color\]**

      * Sets color of the horse
      * Colors Must be uppercase,can be BLACK, BROWN, CHESTNUT, CREAMY, DARK_BROWN, GRAY or WHITE

**Saddled: \[true/false\]**

      * Used for horses to set whether they are saddled or not.
      * Defaults to false.

**HorseStyle: \[horse\_style\]**

      * Sets the style of the horse.
      * Styles can be BLACK_DOTS, WHITE, WHITE_DOTS, WHITEFIELD

**Tamed: \[true/false\]**

      * Used for horses to set whether they are tamed or not.
      * Defaults to false.

**HorseType: \[type\]**

      * Defines the type of horse
      * Can be UNDEAD_HORSE, SKELETON_HORSE, MULE, DONKEY or HORSE
      * Defaults to HORSE
      * Removed in MC 1.11+, use [[databases/mobs/types|mob type]] instead.

#### Iron Golem

**PlayerCreated: \[true/false\]**

      * Acts as if the player built the mob.
      * Defaults to false.

#### Ocelots

**Ocelot: \[type\] (4.9)**

      * Sets the type of ocelot
      * Types can be BLACK_CAT, RED_CAT, SIAMESE_CAT, WILD_OCELOT
      * Defaults to WILD_OCELOT

#### Panda

**MainGene: \[Gene Type\] (4.9)**\*

      * Sets the main gene that the panda can pass on to it's offspring.
      * Can be NORMAL, AGGRESSIVE, LAZY, WORRIED, PLAYFUL, WEAK, BROWN
      * Defaults to NORMAL

**HiddenGene: \[Gene Type\] (4.9)**\*

      * Sets the hidden gene that the panda can pass on to it's offspring.
      * Can be NORMAL, AGGRESSIVE, LAZY, WORRIED, PLAYFUL, WEAK, BROWN
      * Defaults to NORMAL

#### Piglin

**AbleToHunt: \[true/false\] (4.10)**\*

      * Whether or not the piglin is able to hunt
      * Defaults to false

**ImmuneToZombification: \[true/false\] (4.10)**\*

      * Whether or not the piglin is immune to being zombified
      * Defaults to false

#### Piglin Brutes

**ImmuneToZombification: \[true/false\] (4.10)**\*

      * Whether or not the piglin is immune to being zombified
      * Defaults to false

#### Pigs

**Saddled: \[true/false\]**\*

      * Wether or not the pig spawns with a saddle.
      * Defaults to false

#### Rabbits

**RabbitType: \[rabbit\_type\]**

      * Sets type of rabbit
      * Types can be BLACK, BLACK_AND_WHITE, BROWN, GOLD, SALT_AND_PEPPER, THE_KILLER_BUNNY or WHITE

**Baby: \[true/false\]**

      * Not sure why this exists.
      * Defaults to false.

**IsKillerBunny: \[true/false\]**

      * Sets the rabbit as the Killer Bunny.

#### Sheep

**Sheared: \[true/false\]**

      * Sheep is already sheared.
      * Defaults to false.

#### Silverfish

**PreventBlockInfection: \[true/false\]**

      * Prevent silverfish from infecting blocks.
      * Defaults to true.

#### Snow Golem

**Derp: \[true/false\]**

      * Defaults to false.

**PreventSnowFormation: \[true/false\]**

      * Prevent snowmen from creating snow.
      * Defaults to false.

#### TNT

**FuseTicks: \[number\]**

      * How long the TNT takes to explode
      * Defaults to -1 (instantly)

**ExplosionYield: \[number\]**

      * Determines the strength of the explosion
      * Defaults to -1 (none)

**Incendiary: \[true/false\]**

      * Wether the explosion is capable of starting fires
      * Defaults to false

#### Tropical Fish

**Pattern: \[type\]**

      * Sets the shape of the fish
      * Types can be BETTY, BLOCKFISH, BRINELY, CLAYFISH, DASHER, FLOPPER, GLITTER, KOB, SNOOPER, SPOTTY, STRIPEY, or SUNSTREAK.

**BodyColor: \[color\]**

      * Sets the primary color of the fish
      * Color can be BLACK, BLUE, BROWN, CYAN, GRAY, GREEN, LIGHT_BLUE, LIGHT_GRAY, LIME, MAGENTA, ORANGE, PINK, PURPLE, RED, WHITE, or YELLOW.

**PatternColor: \[color\]**

      * Sets the secondary color of the fish
      * Color can be BLACK, BLUE, BROWN, CYAN, GRAY, GREEN, LIGHT_BLUE, LIGHT_GRAY, LIME, MAGENTA, ORANGE, PINK, PURPLE, RED, WHITE, or YELLOW.

#### Villagers

**HasTrades: \[true/false\]**

      * Villager can be traded with.
      * Defaults to false.

**Profession: \[profession\]**

      * Specifies the profession of the villager type mob.
      * Can be ARMORER, BUTCHER, CARTOGROPHER, CLERIC, FARMER, FISHERMAN, FLETCHER, LEATHERWORKER, LIBRARIAN, MASON, NITWIT, NONE, SHEPHERD, TOOLSMITH, WEAPONSMITH.
      * Villagers without this option will roll a random profession on their initial spawn.
      * Examples:
        Profession: MASON

**Type: \[type\]**

      * Represents Villager type, usually corresponding to what biome they spawn in.
      * Can be DESERT, JUNGLE, PLAINS, SAVANNA, SNOW, SWAMP, TAIGA.
      * Defaults to PLAINS.
      * Examples:
        Type: PLAINS

**Level: \[level\]**

      * Villager profession level, levels 1 - 5.
      * Level 1 villagers might switch professions. If you want a villager to hold its profession, give them a level of 2 or higher.
      * Required if setting villager professions.
      
#### Zombies (all variants)

**PreventJockeyMounts: \[true/false\] (4.9)**

      * Sets whether the zombie will spawn as a jockey.
      * Only works for Zombies.
      * Defaults to false.

**PreventTransformation: \[true/false\] (4.8)**

      * Sets whether zombies can be turned into pigmen/drowned.
      * Only works for Zombies.
      * Defaults to false.

**ReinforcementsChance: \[number\]**

      * Chance for zombies to spawn reinforcements on taking damage.
      * Should be a number between 0 and 1 (0% and 100% chance)
      * Only works for Zombies.
      * Defaults to 0.

#### Zombie Villagers

**Profession: \[type\]** (2.4)

      * Sets the type of the villager the zombie should represent.
      * This option will also make the zombie turn into the respective villager type when being cured using potions.
      * Can be "FARMER", ... FIXME

------------------------------------------------------------------------

### Group specific options

#### Breedable mobs

**Age: \[number\]**

      * -1 for Baby. 1 for Adults
      * What the age of the mob will be.
      * Usable on any mob that can age. For example: Sheep, Pigs, Cows...
      * Defaults to 1.
      * Use very low negative numbers to mess with the mobs model (not supported)
      * May not be working properly

**AgeLock: \[true/false\]**

      * Whether the mobs age should be locked in place.
      * Useful for keeping a baby mob from growing up over time.
      * Defaults to false
      * This is required if you want Age option to work

**Baby: \[true/false\]**

      * Sets baby/adult status of mob.
      * Use if **Age: [number]** does not work.

#### Colorable Mobs

Used for sheep and wolves.

**Color: \[number\]**

      * Number between 0 and 15
      * Sets the wool color of sheep or the collar color of wolves
      * **NOTE: in MythicMobs 2.0.0 this has changed to a string value.**
      * **The string is the name of the color you want. Ex: Color: RED**
      * [[http://minecraft.gamepedia.com/Wool|http://minecraft.gamepedia.com/Wool]]

#### Neutral mobs

Used for wolves and zombie pigmen.

**Angry: \[true/false\]**

      * Whether the mob will spawn angry or not.
      * **Note: Due to a Bukkit/Spigot bug wolves can not be spawned angry with this option.**
      * **Use AIGoalSelectors and AITargetSelectors if you want to spawn angry wolves.**

#### Slimes & Magma Cubes

**PreventSlimeSplit: \[true/false\]**

      * Prevents slimes and magmacubes from splitting.

**Size: \[number\]**

      * Sets the size of slimes, magma cubes, and phantoms.
      * Normal slimes are between 1 and 8.
      * Can get VERY big and get exponentially larger with each increase.
      * Extremely high size will cause server lag and possibly crashes.

#### Tameable Mobs

**Tameable: \[true/false\]**

      * Allows players to tame the mobs. Used for wolves, cats and horses.
      * Defaults to false.

------------------------------------------------------------------------