Potions
=======

<img src="http://fs5.directupload.net/images/160308/5egdz7ot.jpg" width="500" height="150" alt="http://fs5.directupload.net/images/160308/5egdz7ot.jpg" />

Potion Options
--------------

This attribute is used to apply potion effects to potion based items.
Note that potion effects can be added to any kind of item, but will only
have an actual function on potions. The sytax is easy:
```
internal_itemname:
  Id: potion
  Options:
    Color: <RED>,<GREEN>,<BLUE>
  PotionEffects:
  - <type> <duration> <level>
```
**&lt;type&gt;**  
Type of potion effect that should be applied. See below for a list of all options at your disposal.

**&lt;duration&gt;**  
The duration of the potion effect measured in ticks [1].

**&lt;level&gt;**  
The level-modifier for the potion effect. Lowest possible is "0".

**colors**  
The RGB color of the potion, i.e. **Color: 255,0,255** for a purple potion

Potion Effects
--------------

This is a complete list of all potion effects currently useable by MythicMobs. These can be utilized by either potion based items or the [potion mechanic](/skills/mechanics/potion).

| **Potion Type**        | **Description**                                                                                                     |
|------------------------|---------------------------------------------------------------------------------------------------------------------|
| **ABSORPTION**         | Increases the maximum health of an entity with health that cannot be regenerated, but is refilled every 30 seconds. |
| **BLINDNESS**          | Blinds an entity.                                                                                                   |
| **CONDUIT\_POWER**     | Increases underwater visibility and mining speed, prevents drowning.                                                |
| **CONFUSION**          | Warps vision on the client.                                                                                         |
| **DAMAGE\_RESISTANCE** | Decreases damage dealt to an entity.                                                                                |
| **DOLPHINS\_GRACE**    | Increases swimming speed.                                                                                           |
| **FAST\_DIGGING**      | Increases dig speed.                                                                                                |
| **FIRE\_RESISTANCE**   | Stops fire damage.                                                                                                  |
| **GLOWING**            | Makes the target entity glow.                                                                                       |
| **HARM**               | Hurts an entity.                                                                                                    |
| **HEAL**               | Heals an entity.                                                                                                    |
| **HEALTH\_BOOST**      | Increases the maximum health of an entity.                                                                          |
| **HUNGER**             | Increases hunger.                                                                                                   |
| **INCREASE\_DAMAGE**   | Increases damage dealt.                                                                                             |
| **INVISIBILITY**       | Makes the target invisible.                                                                                         |
| **JUMP**               | Increases jump height.                                                                                              |
| **LEVITATION**         | Makes the target entity levitate.                                                                                   |
| **LUCK**               | Grants the target entity luck.                                                                                      |
| **NIGHT\_VISION**      | Allows an entity to see in the dark.                                                                                |
| **POISON**             | Deals damage to an entity over time.                                                                                |
| **REGENERATION**       | Regenerates health.                                                                                                 |
| **SATURATION**         | Increases the food level of an entity each tick.                                                                    |
| **SLOW**               | Decreases movement speed.                                                                                           |
| **SLOW\_DIGGING**      | Decreases dig speed.                                                                                                |
| **SLOW\_FALLING**      | Decreases falling speed and negates all fall damage. Eliminates all damage from thrown ender pearls.                |
| **SPEED**              | Increases movement speed.                                                                                           |
| **UNLUCK**             | Grants the target entity bad luck.                                                                                  |
| **WATER\_BREATHING**   | Allows breathing underwater.                                                                                        |
| **WEAKNESS**           | Decreases damage dealt by an entity.                                                                                |
| **WITHER**             | Deals damage to an entity over time and gives the health to the shooter.                                            |

Pre-Made Potion Types and Effects
---------------------------------

If you'd rather use one of the default Minecraft potion types, here are
some common Data values you can use with the POTION item type to make
them!

| **DATA - Regular** | **DATA - Splash** | **DATA - Lingering** | **Potion**                    | **Effect**                                                            |
|--------------------|-------------------|----------------------|-------------------------------|-----------------------------------------------------------------------|
| 8193               | 16385             |                      | Regeneration Potion (0:45)    | Heals 18 over 45 seconds                                              |
| 8194               | 16386             |                      | Swiftness Potion (3:00)       | Increase movement speed by 20% for 3 mins                             |
| 8195               | 16387             |                      | Fire Resistance Potion (3:00) | Immunity to fire for 3 minutes                                        |
| 8196               | 16388             |                      | Poison Potion (0:45)          | 36 damage over 45 seconds                                             |
| 8197               | 16389             |                      | Healing Potion                | Heals 4 instantly                                                     |
| 8198               | 16390             |                      | Night Vision Potion (3:00)    | Night vision for 3 minutes                                            |
| 8200               | 16392             |                      | Weakness Potion (1:30)        | Reduced melee damage by 50% for 1 minute 30 seconds                   |
| 8201               | 16393             |                      | Strength Potion (3:00)        | Increase melee damage by 130% for 3 minutes                           |
| 8202               | 16394             |                      | Slowness Potion (1:30)        | Slows by 15% + 15% per tier for 1 minute 30 seconds                   |
| 8204               | 16396             |                      | Harming Potion                | Does 6 damage                                                         |
| 8205               | 16397             |                      | Water Breathing Potion (3:00) | Water breathing for 3 minutes                                         |
| 8206               | 16398             |                      | Invisibility Potion (3:00)    | Invisibility for 3 minutes                                            |
| 8225               | 16417             |                      | Regeneration Potion II (0:22) | Heals 18 over 22.5 seconds                                            |
| 8226               | 16418             |                      | Swiftness Potion II (1:30)    | Increase movement speed by 40% for 1 minute 30 seconds                |
| 8228               | 16420             |                      | Poison Potion II (0:22)       | Does 38 damage over 22.5 seconds                                      |
| 8229               | 16421             |                      | Healing Potion II             | Heals 8 instantly plus 4 per tier                                     |
| 8233               | 16425             |                      | Strength Potion II (1:30)     | Increase melee damage by 260% + 130% per tier for 1 minute 30 seconds |
| 8236               | 16428             |                      | Harming Potion II             | Does 12 damage plus 6 damage per tier                                 |
| 8257               | 16449             |                      | Regeneration Potion (2:00)    | Heals 48 over 2 minutes                                               |
| 8258               | 16450             |                      | Swiftness Potion (8:00)       | Increase movement speed by 20% for 8 minutes                          |
| 8259               | 16451             |                      | Fire Resistance Potion (8:00) | Immunity to fire for 8 minutes                                        |
| 8260               | 16452             |                      | Poison Potion (2:00)          | Does 96 damage over 2 minutes                                         |
| 8262               | 16454             |                      | Night Vision Potion (8:00)    | Night vision for 8 minutes                                            |
| 8264               | 16456             |                      | Weakness Potion (4:00)        | Reduces melee damage by 50% for 4 minutes                             |
| 8265               | 16457             |                      | Strength Potion (8:00)        | Increase melee damage by 130% for 8 minutes                           |
| 8266               | 16458             |                      | Slowness Potion (4:00)        | Slows by 15% + 15% per tier for 4 minutes                             |
| 8269               | 16461             |                      | Water Breathing Potion (8:00) | Water breathing for 8 minutes                                         |
| 8270               | 16462             |                      | Invisibility Potion (8:00)    | Invisibility for 8 minutes                                            |
| 8289               | 16481             |                      | Regeneration Potion II (1:00) | Heals 48 over 1 minute                                                |
| 8290               | 16482             |                      | Swiftness Potion II (4:00)    | Increased movement speed by 40% for 4 minutes                         |
| 8292               | 16484             |                      | Poison Potion II (1:00)       | Does \~101 damage over a minute                                       |
| 8297               | 16489             |                      | Strength Potion II (4:00)     | Increase melee damage by 260% + 130% per tier for 4 minutes           |

Examples
--------

    SupremeHealingPotion:
      Id: potion
      Data: 8195
      Display: '&6Supreme Healing Potion'
      Options:
        HideFlags: true
      PotionEffects:
      - HEAL 60 1
      - CONFUSION 20 0
      Lore:
      - '&8An incredibly potent healing potion'
      - '&8able to cure even tremendous wounds.'
      - '&cNotice: May cause liver failure.'

[1] 20 ticks = 1 second
