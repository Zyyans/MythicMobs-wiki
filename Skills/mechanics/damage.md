Mechanic: Damage
----------------

Damages the targeted entity.

### Attributes

| Attribute        | Aliases | Description                         | Default |
|------------------|---------|-------------------------------------|---------|
| amount           | a       | The amount of damage to deal        | 1       |
| ignoreArmor      | ia      | Whether or not to ignore armor      | false   |
| preventknockback | pkb, pk | Whether or not to prevent knockback | false   |
| preventimmunity  | pi      | Whether or not to ignore immunities | false   |
| element          | type    | Sets the type of damage to be inflicted | false   |

*"preventknockback" and "preventimmunity" were added in version 2.3*  

### Elements
As seen above, the damage mechanic offers the ability to set an "element" for the damage, like so:

    - damage{amount=10;element=FIRE} @target ~onUse
    - damage{amount=10;element=ICE} @target ~onUse

This element can by named anything, and can be used in a mob's DamageModifiers to alter resistance to the damage type as needed:

    DamageModTest: 
      Type: COW 
      DamageModifiers:
        - LIGHTNING 0.1
        - FIRE 2.0
        - AIR 1.0
        - ICE 0.5 
      Skills:
        - message{m="Damaged by <skill.var.damage-type> for <skill.var.damage-amount>"} @PIR{r=50} \~onDamaged

These options can also be used in the "onDamaged" aura, using the `damageMods="FIRE 0.5"` attribute.

### Examples

      Skills:
      - damage{amount=20;ignoreArmor=true} @target ~onTimer:20

This skill above does 20 damage (10 hearts), ignoring armor, to the
mob's target every 1 second (20 ticks).

    FreezeBlast:
      Skills:
      - effect:sound{s=block.fire.extinguish;v=1;p=0.5} @PIR{r=6}
      - effect:particles{p=explode;a=8;vs=0.5;hs=0.5;s=0;y=1;repeat=5;repeatInterval=20} @PIR{r=6}
      - effect:particles{p=drip_water;a=10;vs=0.5;hs=0.5;s=0;y=1;repeat=5;repeatInterval=20} @PIR{r=6}
      - potion{t=SLOW;d=120;l=6} @PIR{r=6}
      - damage{a=120;pkb=true} @PIR{r=6}

A more complex use of the **damage** mechanic can give illusions of say
Ice attacks like the example above. Which uses effects to make the
targets of the mob appear as if they were frozen by using particles (On
a repeating interval to create a sort of lingering frost effect as well)
and inflicting Slowness level 7 (which is -105% movement speed.) slowing
the mob to a halt. Additionally the mechanic inflicts 120 damage (60
hearts) to players within 6 blocks.

### Examples(Premium Required)

      Skills:
      - damage{amount=<caster.var.somevariable> * 0.5 + 1} @target ~onTimer:20

This skill above does "<caster.var.somevariable> * 0.5 + 1" damage
if the varibute: <caster.var.somevariable>'s value is 5,this mechaine will does 3.5 damage