Item Attributes
===============


The attributes section for items made with MythicMobs handles the Minecraft attribute system. It makes it possible to apply different attributes given to the entity wearing/using it depending on the slot.
```
Item:
  Id: item_id
  Attributes:
    Slot:
      Attribute: [number]
```
Attributes in this section also allow number ranges and forced
percentages. See examples at the bottom of the page.

Attributes
----------

**AttackSpeed: \[number\]**

-   Handles the attack speed or cooldown time of the item. Only does something when used on weapons.
-   Using this attribute will override the original attack speed value of the item. Base item attack speed and custom attack speed do not stack. See [Common Items](/items/Common Item Id's) for a list of base attack speed values.

**Armor: \[number\]**

-   Sets the armor stat of the item.
-   Is applicable to all items - not exclusive to armor type items.
-   1 armor = 0.5 plate pieces

**ArmorToughness: \[number\]**

-   Alters the damage reduction percentage of the armor

**Damage: \[number\]**

-   Sets the melee damage of the item.
-   Using this attribute will override the original damage value of the item. Base item damage and custom damage do not stack.
-   1 damage = 0.5 hearts

**Health: \[number\]**

-   Sets the health of the item which will give the wearer extra or minus health.
-   Use positive numbers for extra health and negative numbers for minus health.
-   1 health = 0.5 hearts

**Luck: \[number\]**

-   Sets the luck or bad luck of the item.
-   Use positive numbers for luck and negative numbers for bad luck.

**KnockbackResistance: \[number\]**

-   Sets the knockback resistance of the item.
-   Use *\[number\]%* to force percentage values.
-   Examples: ```KnockbackResistance: 99%```

**MovementSpeed: \[number\]**

-   Sets the movement speed of the item.
-   Use positive numbers for additional speed and negative numbers for minus speed.

Slots
-----

| **Slot** | **Explanation**                                                           |
|----------|---------------------------------------------------------------------------|
| All      | Special option. Will apply the given attributes to all slots.             |
| MainHand | Attributes will only apply if item is being held in the main hand.        |
| OffHand  | Attributes will only apply if item is being held in the off hand.         |
| Head     | Attributes will only apply if item is being worn on the head slot.        |
| Chest    | Attributes will only apply if item is being worn on the chest/torso slot. |
| Legs     | Attributes will only apply if item is being worn on the legs slot.        |
| Feet     | Attributes will only apply if item is being worn on the feet slot.        |

Examples
========

This example item will grant +10 luck when the item is held in the main
hand, but will grant +7 luck and +2 extra damage if the item is held in
the off hand slot:
```
lucky_charms:
  Id: potato_item
  Display: 'Rotten Lucky Charm'
  Attributes:
    MainHand:
      Luck: 10
    OffHand:
      Luck: 7
      Damage: 2
```
This example item grants +2 extra health no matter in which slot the item is being held, but will also grant +4% movement speed if the item is worn in the feet slot:
```
happy_feet:
  Id: leather_boots
  Display: 'Penguin Hide'
  Attributes:
    All:
      Health: 2
    Feet:
      MovementSpeed: 0.04
```
Each time this item is generated it will have a random damage value between 3 and 5 and a random speed bonus between 1 % and 5 % when worn in the main hand:
```
lucky_sword:
  Id: wood_sword
  Display: '&eLucky Sword&r'
  Attributes:
    MainHand:
      Damage: 3-5
      MovementSpeed: 0.01-0.05
```