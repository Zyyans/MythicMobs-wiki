Immunity Tables allow a mob to track each player's damage and assigns NoDamageTicks individually, so that the mob can only take damage every half second PER PLAYER instead of TOTAL. Basically, they allow multiple players hitting a mob to all have their damage count.

**Enabling Immunity Tables**

Turning on Immunity Tables for a mob is easy. Just add Modules.ImmunityTable: true to your mob, like so:

```
BigHealthBoss:
  Type: pig_zombie
  Display: '&6Hungry Hungry Piggy Zombie'
  Health: 20000
  Modules:
    ImmunityTable: true
  Options:
    NoDamageTicks: 10
```

That's it!

Immunity Tables will take the NoDamageTicks option into account if you decide to change it, however it is not necessary and will use Minecraft's default of 10 if one isn't specified.