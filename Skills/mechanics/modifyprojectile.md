Mechanic: ModifyProjectile
==========================

Modifies a projectile, missile, or orbital as it is active.

Attributes
----------

| Attribute | Aliases | Description | Default Value |
|-----------|---------|-------------|---------------|
| trait     |         | the trait to modify. Can be inertia, gravity, velocity, power, and radius | |
| action    |         | SET or MULTIPLY |           |
| value     |         | amount to modify the trait | |

--------

Notes:

Inertia only makes sense to work with Missile

Radius only works with orbitals (4.12 MM)

--------

Examples
--------

in this example when you shoot the projectile you will watch it slow down gradually to a halt. To test this you can cast it using the in game command below after adding it to a skills.yml file.

/mm test cast TestingModifyProjectile


```
TestingModifyProjectile:
  Skills:
  - projectile{oT=TMP_oT;i=1;v=8;d=200;mr=100} @forward{f=100;y=0}
TMP_oT:
  Skills:
  - particles{particle=flame;a=2;hs=0;vs=0;s=0;y=0} @origin
  - modifyProjectile{trait=VELOCITY;action=MULTIPLY;value=0.95}
```