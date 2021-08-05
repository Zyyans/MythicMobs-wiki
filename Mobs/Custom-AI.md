This page includes all the AI Goal and Target Selectors for your mobs. It allows you to change the behavior and functionality.

---
### Goal Selectors

Goal Selectors are used with the AIGoalSelectors field and determine what mobs want to “do”. Certain custom goals might not work if they're not included in the base AI of the mob you're creating. For example, a zombie won't be able to use the AI goal “EatGrass”, because a zombie would never use that goal in the first place. Feel free to experiment however! 

**You also cannot cause a passive mob to attack a target as the event is not handled and will crash the server.**


---
**Example:**
```
ZombieAIMob:
  Type: ZOMBIE
  Health: 125
  Display: 'Custom AI Zombie'
  AIGoalSelectors:
  - 0 clear
  - 1 meleeattack
  - 2 randomstroll
```

**Breaking down the example:**
```
- 0 clear        [Clears the mob AI, will be explained down below]
- 1 meleeattack  [Tells your mob to use a melee attack against its targets]
- 2 randomstroll [Tells your mob to wander around]
```
The order 0 - 1 - 2 is made to set priority over some AI Goals, by putting meleeattack at 1 and randomstroll at 2, the mob will priorize melee attacking its targets than randomly wandering around. Experiment with it!

---

### Mobs - Goal and Target

**Goal: All Mobs**

| AI Goal | Alias  | Description |
| ------- | ------ | ----------- |
| clear            | reset    | Removes the AI from the mob. Useful to build custom mobs behavior. |
| breakdoors       |          | Causes the mob to break down doors it runs into. |
| eatgrass         |          | Makes the mob occasionally eat grass. |
| float            | swim     | Allows the mob to float in water, without this, mobs sink. |
| lookatplayers    |          | The mob will look at nearby players. |
| opendoors        | opendoor | Allows the mob to open doors they come across. |
| closedoors       | restrictopendoor | **Not tested yet.** |
| randomlookaround | lookaround       | Will cause the mob to randomly look around. |

**Target:**
