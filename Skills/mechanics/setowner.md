Mechanic: SetOwner
==================

Added in MM 4.0.0

Sets the "owner" attribute of the Mythic Mob to the given target. Does
nothing if the caster is not a Mythic Mob. Works with the @Owner target,
and the Owner target condition.

Special Notes
-------------

This is used in conjunction with the **owner condition** (see
[Conditions](/conditions/start#targettrigger_only_conditions)) and
@Owner targets.  
This is NOT the same as a owner for a wolf or ocelot.

Examples
--------

    PetSheep:
      Mobtype: sheep
      Display: 'Pet'
      Health: 20
      Damage: 18
      Skills:
      - skill{s=SetOwner} @trigger ~onInteract
      - skill{s=HealOwner} @PIR{R=10} ~onTimer:50
     

This skill would change the mob's owner to whoever right clicked it.

    SetOwner:
      Skills:
      - setowner @trigger

This skill would only heal the owner of the mob

    HealOwner:
      TargetConditions:
      - owner true
     Skills:
      - heal{a=10}
