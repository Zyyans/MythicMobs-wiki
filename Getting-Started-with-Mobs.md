MythicMobs is a highly customizable Mob creation plugin, where you can create your very own Mobs and Bosses based on YAML files. The level of complexity is up to you, make just a simple Zombie with armor or a massive Boss with minions, skills, custom drops and AI.

---
### Creating the file:
To create your first mob, navigate to the ``MythicMobs/Mobs`` folder and create a YAML file named ``tutorial_mob.yml``. (Do note, you can name it as you wish, but for sake of simplicity we will be using this file name on this tutorial.)

### Setting up basics:
Now that you have the mob file, lets start by populating it with your very own mob:
```
# Internal name used by MythicMobs, this must be an alpha numeric, unique value as its how the mob is identified by the plugin.
tutorial_pirate:

  # Base mob type, must be a valid Minecraft Entity.
  Type: ZOMBIE

  # A String that will be used as the mob display name, can include color codes.
  Display: '&ePirate'

  # Base Mob health.
  Health: 100

  # Base Mob damage.
  Damage: 10

  # The equipment that the mob uses, in this current setup, it equips an Iron Sword on the Main Hand and a Shield on the Offhand. 
  # Check Equipment for more info: https://git.mythiccraft.io/mythiccraft/MythicMobs/-/wikis/Mobs/Equipment
  Equipment:
  - IRON_SWORD HAND
  - SHIELD OFFHAND

  # Customization Options for mobs:
  # More options on: https://git.mythiccraft.io/mythiccraft/MythicMobs/-/wikis/Mobs/Options
  Options:
    # - If true, always show the display name as nametag.
    AlwaysShowName: true
    # - If true, disable vanilla drops.
    PreventOtherDrops: true
    # - If true, the mob won't burn in sunlight.
    PreventSunburn: true

  # Sets the mob faction, useful for AI and combat. 
  Faction: PIRATE

  Skills:
  - message{msg="I will crush your bones!"} @PIR{r=10} ~onSpawn
  - sound{s=entity.player.attack.sweep} @Self ~onAttack
  - effect:particles{particle=sweep_attack;amount=1} @Self ~onAttack
  - message{msg="How could I be defeated?!"} @PIR{r=10} ~onDeath
``` 

### Explanation:
```
tutorial_pirate:
```
Sets the internal mob ID to "tutorial_pirate".

```
  Type: ZOMBIE
```
Sets the entity type as Zombie.

```
  Display: '&ePirate'
```
Sets the entity display name as 'Pirate' with yellow color.

```
  Health: 100
```
Defines the default mob health to 100.

```
  Damage: 10
```
Defines the base mob damage to 10.

```
  Equipment:
  - IRON_SWORD HAND
  - SHIELD OFFHAND
```
Equips an Iron Sword on the Main Hand and a Shield on the Offhand. 

```
  Options:
    AlwaysShowName: true
    PreventOtherDrops: true
    PreventSunburn: true
```
Options to customize the mob, this setup makes:
- Display name always show.
- Prevents vanilla drops.
- Prevents the mob from burning in Daylight. 

```
  Faction: PIRATE
```
Sets the faction of the mob as "Pirate".

```
  Skills:
  - message{msg="I will crush your bones!"} @PIR{r=10} ~onSpawn
  - sound{s=entity.player.attack.sweep} @Self ~onAttack
  - effect:particles{particle=sweep_attack;amount=1} @Self ~onAttack
  - message{msg="How could I be defeated?!"} @PIR{r=10} ~onDeath
```
SKILLS TBA.

---
### Example Mob:
```
tutorial_pirate:
  Type: ZOMBIE
  Display: '&ePirate'
  Health: 100
  Damage: 10
  Equipment:
  - IRON_SWORD HAND
  - SHIELD OFFHAND
  Options:
    AlwaysShowName: true
    PreventOtherDrops: true
    PreventSunburn: true
  Faction: PIRATE
  Skills:
  - message{msg="I will crush your bones!"} @PIR{r=10} ~onSpawn
  - sound{s=entity.player.attack.sweep} @Self ~onAttack
  - effect:particles{particle=sweep_attack;amount=1} @Self ~onAttack
  - message{msg="How could I be defeated?!"} @PIR{r=10} ~onDeath
``` 


# TODO