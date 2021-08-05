This page contains a list of all available AI Goals in MythicMobs.

---

**Goal Selectors**
---
Goal Selectors are used with the AIGoalSelectors field and determine what mobs want to “do”. Certain custom goals might not work if they're not included in the base AI of the mob you're creating. For example, a zombie won't be able to use the AI goal “EatGrass”, because a zombie would never use that goal in the first place. Feel free to experiment however! You also cannot cause a passive mob to attack a target as the event is not handled and will crash the server.

Example:

```
SuperMob:
  Type: zombie
  Health: 200
  Display: 'Superb Zombie'
  AIGoalSelectors:
  - clear
  - meleeattack
  - randomstroll
```

This zombie would attack players, and walk around randomly when not targeting an enemy.

**All Mobs**

| AI Goal       | Aliases          | Description                                           |
| ------------- | ---------------- | ----------------------------------------------------- |
| clear         | reset            | Removes the AI from the mob                           |
| breakdoors    |                  | Causes the mob to break down doors it runs into       |
| eatgrass      |                  | Makes the mob occasionally… eat grass                 |
| float         | swim             | Makes the mob swim in water/not sink                  |
| lookatplayers |                  | The mob will look at nearby players                   |
| opendoors     | opendoor         | The mob will open doors it runs into and close the door behind it |
| closedoors    | restrictopendoor | Not sure what this one does                           |
| randomlookaround | lookaround    | The mob will randomly look around                     |
| gotospawnlocation | gotospawn    | Mob will pathfind to the its spawn location         |
| fleeConditional **[Premium-only]** | fleeIf  | Causes the mob to flee based on provided conditions.  |
| doNothing **[Premium-only]** |                  | Causes the mob to do nothing if conditions are met |

FleeConditional Example:
```
AIGoalSelectors:
- clear
- fleeConditional{distance=5; speed=2; conditions=[
      - inlineofsight true
      - entitytype COW true
    ]}
```

**Creatures Only**

| AI Goal       | Aliases          | Description                                           |
| ------------- | ---------------- | ----------------------------------------------------- |
| avoidcreepers |                  | Causes the mob to avoid Creepers                      |
| avoidskeletons |                 | Causes the mob to avoid Skeletons                     |
| avoidzombies  |                  | Causes the mob to avoid Zombies                       |
| fleesun       |                  | The mob will hide in the shade when the sun it out    |
| meleeattack   |                  | Causes the mob to move to and melee-attack its target |
| movetowardstarget |              | Causes the mob to move towards its target             |
| randomstroll  |                  | The mob will randomly walk around                     |
| restrictsun   |                  | In theory this will keep the mob from entering sunlight |
| fleeplayers   | runfromplayers   | Causes the mob to avoid Players                       |
| fleegolems    | runfromgolems    | Causes the mob to avoid Iron Golems                   |
| fleevillagers | runfromvillagers  | Causes the mob to avoid villagers                     |
| fleewolves    | runfromwolves  | Causes the mob to avoid wolves                        |
| spiderattack  |                  | Uses the attack a spider would (doesn't seem any different from a meleeattack) |
| leapattarget  |                  | Makes the mob leap at its target                      |
| moveindoors   | | |
| movethroughvillage | | |
| movetowardsrestriction | | |
| patrol x1,y1,z1;x2,y2,z2;x3,y3,z3;… | patrolroute | Makes the mob patrol between the specified locations |
| gotolocation x,y,z | goto        | Makes the mob go to the specified location(Notice Followrange must more than the distance between location and mob)            |
| gotoowner #   |                  | Makes the mob move towards its owner when beyond a certain distance (defaults to 5 blocks,Notice Followrange must more than the distance between location and mob) |
| gotoparent    |                  | Makes the mob move towards its parent mob             |
| panicWhenOnFire | panic              | Run around panicking when on fire and look for water |

**Ranged Entities Only**

| AI Goal       | Aliases          | Description                                           |
| ------------- | ---------------- | ----------------------------------------------------- |
| arrowattack   |                  | Projectile attack (shooting a bow for a skeleton)     |
| skeletonbowattack | bowshoot, bowmaster | The new strafing AI for skeletons in Minecraft 1.9 and up |

**Piglins and Pillagers Only**

| AI Goal       | Aliases          | Description                                           |
| ------------- | ---------------- | ----------------------------------------------------- |
| crossbowAttack   |                  | attack with a crossbow     |

**Target Selectors**
---
Target Selectors are used with the AITargetSelectors field and determine what mobs want to target.

Example:

```
SuperMob:
  Type: zombie
  Health: 200
  Display: 'Superb Zombie'
  AIGoalSelectors:
  - clear
  - meleeattack
  - randomstroll
  AITargetSelectors:
  - clear
  - players
  - golems
```

**All Creatures**

| AI Goal       | Aliases          | Description                                           |
| ------------- | ---------------- | ----------------------------------------------------- |
| clear         |                  | Special Option. Clears all of the mob's AI.           |
| attacker      | hurtbytarget, damager | Targets whatever attacks the mob                      |
| monsters      |                  | Targets monsters.                                     |
| players       |                  | Targets players.                                      |
| villagers     |                  | Targets villagers.                                    |
| golems        |                  | Targets Golems.                                       |
| nearestConditionalTarget **[Premium-only]** | nearestConditional, nearestIf      | Targets the nearest entity that meets the conditions provided. |

NearestConditionalTarget Example:
```
AITargetSelectors:
- clear
- nearestConditionalTarget{conditions=[
      - entitytype PLAYER true
      - hasaura{aura=marked_for_death} true
    ]}
```

**All Creatures(Faction Support)**

| AI Goal       | Description                                           |
| ------------- | ----------------------------------------------------- |
| OtherFaction  | Targets ANY entities that are in a different faction. |
| OtherFactionMonsters | Targets any monsters that are in a different faction. |
| OtherFactionVillagers |  Targets any villagers that are in a different faction. |
| SpecificFaction [faction_name] | Targets any entities that are in the given faction. |
| SpecificFactionMonsters [faction_name] | Targets any monsters that are in the given faction. |

Example:

```
AITargetSelectors:
- SpecificFaction undead
```

This will force a mob to attack mobs only in the “undead” faction.

**Tameable Creatures**

| AI Goal       | Description                                           |
| ------------- | ----------------------------------------------------- |
| ownerattacker | Targets whatever attacks the mob's owner.             |
| ownertarget   | Targets whatever the mob's owner attacks.             |