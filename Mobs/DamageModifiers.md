**Damage Modifiers**

Damage Modifiers are an attribute you can add to your MythicMobs to increase or decrease the damage they receive from various sources.

Some of these won't work on mobs (such as SUICIDE) under normal circumstances.

Also working on some mechaines,such as the damage caused by ignite will be affected

Damage Modifiers are completely optional, you only need to add the ones you want to use.

**Options**

| Modifier      | Explanation                                           |
| ------------- | ----------------------------------------------------- |
| DROWNING      | Damage caused by running out of air while in water.   |
| BLOCK_EXPLOSION | Damage caused by being near an exploding block.     |
| ENTITY_EXPLOSION | Damage caused by being in the area when an entity, such as a Creeper, explodes. |
| VOID          | Damage caused by falling into the void.               |
| LIGHTNING	    | Damage caused by being struck by lightning.           |
| SUICIDE       | Damage caused by committing suicide using the command “/kill”. |
| STARVATION    | Damage caused by starving due to having an empty hunger bar. |
| POISON        | Damage caused due to an ongoing poison effect. |
| MAGIC         | Damage caused by being hit by a potion or spell. |
| DRAGON_BREATH	| Damage caused by being hit by the enderdragon's breath. |
| WITHER        | Damage caused by the Wither potion effect. |
| FALLING_BLOCK | Damage caused by being hit by a falling block which deals damage. |
| THORNS        | Damage caused in retaliation to another attack by the Thorns enchantment. |
| CUSTOM        | Damage caused by “Custom” sometimes used by other plugins. |
| LAVA          | Damage caused by touching lava. |
| MELTING       | Damage caused by a snowman melting. |
| FIRE_TICK     | Damage caused due to an ongoing fire effect. |
| FIRE          | Damage caused by touching fire. |
| HOT_FLOOR     | Damage caused by standing on magma blocks. |
| FALL          | Damage caused when an entity falls a distance greater than 3 blocks. |
| SUFFOCATION   | Damage caused by standing inside of a block. |
| PROJECTILE    | Damage caused when attacked by a projectile. |
| ENTITY_ATTACK | Damage caused when an entity attacks another entity. |
| CONTACT       | Damage caused when an entity touches a block such as a cactus. |

**Examples**

NOTE: A modifier of 1 will cause the mob to take normal damage from that source, a number higher than 1 will increase the damage it takes by that amount. A number lower than 1 will reduce the damage it takes by that amount. And a 0 will make the mob immune to that damage source.
A negative value (below 0) will cause the mob to heal from that type of damage. Note that this doesn't work if the mob is naturally immune to that damage. (e.g. Iron Golems and fall damage, Blazes and fire tick/lava damage)

In this first example our Armored Zombie mob is just a basic MythicMob with nothing added to it.

```
ArmoredZombie:
  Mobtype: zombie
  Display: '&aArmored Zombie'
  Health: 40
  Damage: 6
```

But, if we add the DamageModifiers attribute to him we can start messing around with his weaknesses and resistances. In this example we are going to make it so melee and projectile attacks only do 75% of their normal damage to our Armored Zombie.

```
ArmoredZombie:
  Mobtype: zombie
  Display: '&aArmored Zombie'
  Health: 40
  Damage: 6
  DamageModifiers:
  - ENTITY_ATTACK 0.75
  - PROJECTILE 0.75
```

Alright, we have our damage resistant zombie now. Any melee and projectile damage it receives will be reduced by 25% (This includes from players and other mobs.) but now he seems a little overpowered, so, lets give him a weakness to go along with it.

```
ArmoredZombie:
  Mobtype: zombie
  Display: '&aArmored Zombie'
  Health: 40
  Damage: 6
  DamageModifiers:
  - ENTITY_ATTACK 0.75
  - PROJECTILE 0.75
  - MAGIC 1.25
```

OK, I'd say he's just about done now. Our little Armored Zombie is now well protected against projectile and melee attacks but we gave him a nice weakness to magic (splash health potions).

——————-
Our second example is a fire elemental- not only does this mob not take damage from burning, it also heals health when standing in fire, and regains even more health when in lava. Note: This DOES NOT work on Nether mobs as they don't take damage from fire at all, preventing them from having their fire and lava damage modified.

```
FireElemental:
  Mobtype: zombie
  Display: '&cFire Elemental'
  Health: 20
  DamageModifiers:
  - FIRE -1
  - LAVA -4
  - FIRE_TICK 0
```