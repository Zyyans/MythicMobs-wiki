Single Target Fire
---------------------
* Basic
```
SingleTargetFire:
  Cooldown: 1
  Skills:
  - effect:particles{p=flame;hs=1;vs=1;a=50;s=0.01;} @target  
  - damage{a=6;ignorearmor=true;}
  - ignite{d=60;}
```
* Advanced: Casting time, mob stops to cast
```
SingleTargetFire:
  Cooldown: 1
  Skills:
  - message{msg="<mob.name>&e begins casting a spell."} @PIR{r=15}
  - potion{type=SLOW;d=40;level=7;} @self
  - delay 40
  - message{m="<target.name> &ecombusts."} @PIR{r=20}
  - effect:particles{p=largesmoke;vs=1;hs=1;a=50;s=0.01;}
  - effect:particles{p=flame;hs=1;vs=1;a=50;s=0.01;} @target
  - effect:particles{p=explode;vs=1;hs=1;a=50;s=0.01;}
  - effect:sound{s=entity.ghast.fireball;v=1;p=1;}
  - damage{a=6;ignorearmor=true;}
  - ignite{d=60;}
```
* Advanced: Casting time. Mob stops to cast, conditions and GCD
```
SingleTargetFire:
  Cooldown: 1
  Conditions:
  - targetwithin 15
  - targetinlineofsight true
  - offgcd true
  Skills:
  - GCD{t=40}
  - message{msg="<mob.name>&e begins casting a spell."} @PIR{r=15}
  - potion{type=SLOW;d=40;level=7;} @self
  - delay 40
  - message{m="<target.name> &ecombusts."} @PIR{r=20}
  - effect:particles{p=largesmoke;vs=1;hs=1;a=50;s=0.01;}
  - effect:particles{p=flame;hs=1;vs=1;a=50;s=0.01;} @target
  - effect:particles{p=explode;vs=1;hs=1;a=50;s=0.01;}
  - effect:sound{s=entity.ghast.fireball;v=1;p=1;}
  - damage{a=6;ignorearmor=true;}
  - ignite{d=60;}
```
AOE Fire
------------------------
* Basic
```
AOEFire:
  Cooldown: 1
  Skills:
  - effect:particles{p=flame;hs=10;vs=1;a=1000;s=0.01;} 
  - damage{a=6;ignorearmor=true;} @PIR{r=10}
  - ignite{d=60;} @PIR{r=10}
```
* Advanced: Casting time, mob stops to cast
```
AOEFire:
  Cooldown: 1
  Skills:
  - message{msg="<mob.name>&e begins casting a spell."} @PIR{r=15}
  - potion{type=SLOW;d=80;level=7;}
  - delay 80
  - message{m="<target.name>&e combusts."} @PIR{r=20}
  - effect:particles{p=reddust;hs=10;vs=1;a=1000;s=0.01;}
  - effect:particles{p=flame;hs=10;vs=1;a=1000;s=0.01;}
  - effect:sound{s=entity.ghast.fireball;v=1;p=1;}
  - damage{a=6;ignorearmor=true;} @PIR{r=10}
  - ignite{d=60;} @PIR{r=10}
```
* Advanced: Casting time. Mob stops to cast, conditions and GCD
```
AOEFire:
  Cooldown: 1
  Conditions:
  - targetwithin 20
  - offgcd true
  Skills:
  - GCD{t=80}
  - message{msg="<mob.name>&e begins casting a spell."} @PIR{r=15}
  - potion{type=SLOW;d=80;level=7;}
  - delay 80
  - message{m="<target.name>&e combusts."} @PIR{r=20}
  - effect:particles{p=reddust;hs=10;vs=1;a=1000;s=0.01;}
  - effect:particles{p=flame;hs=10;vs=1;a=1000;s=0.01;} @self
  - effect:sound{s=entity.ghast.fireball;v=1;p=1;}
  - damage{a=6;ignorearmor=true;} @PIR{r=10}
  - ignite{d=60;} @PIR{r=10}
```
Single Target Frost
---------------------
* Basic
```
SingleTargetFrost:
  Cooldown: 1
  Skills:
  - effect:particles{p=splash;vs=1;hs=1;a=100;s=0.01}
  - effect:sound{s=block.fire.extinguish;v=2;p=1;}
  - damage{a=3;i=true;}
  - potion{type=SLOW;d=60;level=3;} 
```
* Advanced: Casting time, mob stops to cast
```
SingleTargetFrost:
  Cooldown: 1
  Skills:
  - message{m="$boss &ebegins casting a spell."} @PIR{r=20}
  - potion{type=SLOW;d=40;level=7;} @self
  - delay 40
  - message{m="<target.name>&e is frozen."} @PIR{r=20}
  - effect:particles{p=splash;vs=1;hs=1;a=100;s=0.01}
  - effect:sound{s=block.fire.extinguish;v=1;p=1;}
  - damage{a=3;i=true;}
  - potion{type=SLOW;d=60;level=3;} 
```
* Advanced: Casting time. Mob stops to cast, conditions and GCD
```
SingleTargetFrost:
  Cooldown: 1
  Conditions:
  - targetwithin 15
  - targetinlineofsight true
  - offgcd true
  Skills:
  - GCD{t=40}
  - message{m="$boss &ebegins casting a spell."} @PIR{r=20}
  - potion{type=SLOW;d=40;level=7;} @self
  - delay 40
  - message{m="<target.name>&e is frozen"} @PIR{r=20}
  - effect:particles{p=splash;vs=1;hs=1;a=100;s=0.01}
  - effect:sound{s=block.fire.extinguish;v=1;p=1;}
  - damage{a=3;i=true;}
  - potion{type=SLOW;d=60;level=3;} 
```
AOE Frost
--------------
* Basic
```
AOEFrost:
  Cooldown: 1
  Skills:
  - effect:particles{p=splash;hs=5;vs=1;a=5000;s=0.01;y=1}
  - effect:sound{s=block.fire.extinguish;v=2;p=1;}
  - damage{a=6;ignorearmor=true;} @PIR{r=10}
  - potion{type=SLOW;d=60;level=3;} @PIR{r=10}
```
* Advanced: Casting time, mob stops to cast
```
AOEFrost:
  Cooldown: 1
  Skills:
  - message{msg="<mob.name>&e begins casting a spell."} @PIR{r=15}
  - potion{type=SLOW;d=80;level=7;} @self
  - delay 80
  - message{m="<target.name>&e is frozen"} @PIR{r=20}
  - effect:particles{p=splash;hs=5;vs=1;a=5000;s=0.01;y=1}
  - effect:sound{s=block.fire.extinguish;v=2;p=1;}
  - damage{a=6;ignorearmor=true;} @PIR{r=10}
  - potion{type=SLOW;d=60;level=3;} @PIR{r=10}
```
* Advanced: Casting time. Mob stops to cast, conditions and GCD
```
AOEFrost:
  Cooldown: 1
  Conditions:
  - targetwithin 20
  - offgcd true
  Skills:
  - GCD{t=80}
  - message{msg="<mob.name>&e begins casting a spell."} @PIR{r=15}
  - potion{type=SLOW;d=80;level=7;} @self
  - delay 80
  - message{m="<target.name>&e is frozen"} @PIR{r=20}
  - effect:particles{p=splash;hs=5;vs=1;a=5000;s=0.01;y=1}
  - effect:sound{s=block.fire.extinguish;v=2;p=1;}
  - damage{a=6;ignorearmor=true;} @PIR{r=10}
  - potion{type=SLOW;d=60;level=3;} @PIR{r=10}
```
Single Target Lightning
----------------------
* Basic
```
SingleTargetLightning:
  Cooldown: 1
  Skills: 
  - lightning{d=5;}
  - delay 5
  - effect:particles{p=fireworksSpark;vs=1;hs=1;a=100;s=1;}
```
* Advanced: Casting time, mob stops to cast
```
SingleTargetLightning:
  Cooldown: 1
  Skills: 
  - message{m="$boss &ebegins casting a spell."} @PIR{r=20}
  - potion{type=SLOW;d=60;level=7;} @self
  - delay 60
  - lightning{d=5;}
  - message{m="<target.name>&e is shocked."} @PIR{r=20}
  - delay 5
  - effect:smoke @target
  - effect:particles{p=fireworksSpark;vs=1;hs=1;a=100;s=1;}
  - effect:particles{p=reddust;vs=1;hs=1;a=500;s=0.01;}
```
* Advanced: Casting time. Mob stops to cast, conditions and GCD
```
SingleTargetLightning:
  Cooldown: 1
  Conditions:
  - targetwithin 15
  - targetinlineofsight true
  - offgcd true
  Skills:
  - GCD{t=60}
  - message{m="$boss &ebegins casting a spell."} @PIR{r=20}
  - potion{type=SLOW;d=60;level=7;} @self
  - delay 60
  - lightning{d=5;}
  - message{m="<target.name>&e is shocked."} @PIR{r=20}
  - delay 5
  - effect:smoke @target
  - effect:particles{p=fireworksSpark;vs=1;hs=1;a=100;s=1;}
  - effect:particles{p=reddust;vs=1;hs=1;a=500;s=0.01;}
```
AOE Lightning
----------------
* Basic
```
AOELightning:
  Cooldown: 1
  Skills: 
  - lightning{d=18;} @PIR{r=10}
  - delay 5
  - effect:particles{p=fireworksSpark;vs=1;hs=5;a=100;s=1;}
```
* Advanced: Casting time, mob stops to cast
```
AOELightning:
  Cooldown: 1
  Skills: 
  Cooldown: 1
  Skills: 
  - message{m="$boss &ebegins casting a spell."} @PIR{r=20}
  - potion{type=SLOW;d=80;level=7;} @self
  - delay 80
  - message{m="<target.name>&e is shocked."} @PIR{r=20}
  - lightning{d=18;} @PIR{r=10}
  - delay 5
  - effect:smoke
  - effect:particles{p=fireworksSpark;vs=1;hs=5;a=100;s=1;}
  - effect:particles{p=reddust;vs=1;hs=5;a=100;s=0.01;}
```
* Advanced: Casting time. Mob stops to cast, conditions and GCD
```
AOELightning:
  Cooldown: 1
  Conditions:
  - targetwithin 20
  - offgcd true
  Skills:
  - GCD{t=80}
  - message{m="$boss &ebegins casting a spell."} @PIR{r=20}
  - potion{type=SLOW;d=80;level=7;} @self
  - delay 80
  - message{m="<target.name>&e is shocked."} @PIR{r=20}
  - lightning{d=18;} @PIR{r=10}
  - delay 5
  - effect:smoke
  - effect:particles{p=fireworksSpark;vs=1;hs=5;a=100;s=1;}
  - effect:particles{p=reddust;vs=1;hs=5;a=100;s=0.01;}
```
AOE Lightning Storm
--------------------
* Advanced: Casting time. Mob stops to cast, conditions and GCD, multiple strikes
```
AOELightningStorm:
  Cooldown: 1
  Conditions:
  - targetwithin 20
  - offgcd true
  Skills:
  - GCD{t=80}
  - message{m="$boss &ebegins casting a spell."} @PIR{r=20}
  - potion{type=SLOW;d=80;level=7;} @self
  - delay 80
  - message{m="<target.name>&e is consumed by lightning."} @PIR{r=20}
  - lightning 10:3
  - delay 5
  - effect:smoke
  - effect:particles{p=fireworksSpark;vs=1;hs=5;a=100;s=1;}
  - effect:particles{p=reddust;vs=1;hs=5;a=100;s=0.01;}
  - delay 10
  - lightning 10:3
  - delay 5
  - effect:smoke
  - effect:particles{p=fireworksSpark;vs=1;hs=5;a=100;s=1;}
  - effect:particles{p=reddust;vs=1;hs=5;a=100;s=0.01;}
  - delay 10
  - lightning 10:3
  - delay 5
  - effect:smoke
  - effect:particles{p=fireworksSpark;vs=1;hs=5;a=100;s=1;}
  - effect:particles{p=reddust;vs=1;hs=5;a=100;s=0.01;}
  - delay 10
  - lightning 10:3
  - delay 5
  - effect:smoke
  - effect:particles{p=fireworksSpark;vs=1;hs=5;a=100;s=1;}
  - effect:particles{p=reddust;vs=1;hs=5;a=100;s=0.01;}
  - delay 10
  - lightning 10:3
  - delay 5
  - effect:smoke
  - effect:particles{p=fireworksSpark;vs=1;hs=5;a=100;s=1;}
  - effect:particles{p=reddust;vs=1;hs=5;a=100;s=0.01;}
  - delay 10
  - lightning 10:3
  - delay 5
  - effect:smoke
  - effect:particles{p=fireworksSpark;vs=1;hs=5;a=100;s=1;}
  - effect:particles{p=reddust;vs=1;hs=5;a=100;s=0.01;}
```
Single Target DOT
--------------------
* Basic
```
SingleTargetDOT:
  Cooldown: 1
  Skills:
  - effect:particles{p=happyVillager;hs=1;vs=1;a=250;s=0.5;}
  - effect:sound{s=entity.spider.ambient;v=2;p=1;}
  - potion{type=POISON;d=200;level=1;}
  - potion{type=SLOW;d=80;level=7;} @self
```
* Advanced: Casting time, mob stops to cast
```
SingleTargetDOT:
  Cooldown: 1
  Skills:
  - message{m="$boss&e begins casting a spell"} @PIR{r=20}
  - potion{type=SLOW;d=80;level=7;} @self
  - delay 80
  - message{m="<target.name>&e is poisoned."} @PIR{r=20}
  - effect:particles{p=happyVillager;hs=1;vs=1;a=250;s=0.5;}
  - effect:sound{s=entity.spider.ambient;v=2;p=1;}
  - potion{type=POISON;d=200;level=1;}
```
* Advanced: Casting time. Mob stops to cast, conditions and GCD
```
SingleTargetDOT:
  Cooldown: 1
  Conditions:
  - targetwithin 15
  - targetinlineofsight true
  - offgcd true
  Skills:
  - GCD{t=80}
  - message{m="$boss&e begins casting a spell"} @PIR{r=20}
  - potion{type=SLOW;d=80;level=7;} @self
  - delay 80
  - message{m="<target.name>&e is poisoned."} @PIR{r=20}
  - effect:particles{p=happyVillager;hs=1;vs=1;a=250;s=0.5;}
  - effect:sound{s=entity.spider.ambient;v=2;p=1;}
  - potion{type=POISON;d=200;level=1;}
```
AOE DOT
----------------
* Basic
```
AOEDOT:
  Cooldown: 1
  Skills:
  - effect:particles{p=happyVillager;hs=1;vs=1;a=250;s=0.5;}
  - effect:sound{s=entity.spider.ambient;v=2;p=1;}
  - potion{type=POISON;d=200;level=1;} @PIR{r=10}
```
* Advanced: Casting time, mob stops to cast
```
AOEDOT:
  Cooldown: 1
  Skills:
  - message{m="$boss&e begins casting a spell"} @PIR{r=20}
  - potion{type=SLOW;d=80;level=7;} @self
  - delay 80
  - message{m="<target.name>&e is poisoned."} @PIR{r=20}
  - effect:particles{p=happyVillager;hs=1;vs=1;a=250;s=0.5;}
  - effect:sound{s=entity.spider.ambient;v=2;p=1;}
  - potion{type=POISON;d=200;level=1;} @PIR{r=10}
```
* Advanced: Casting time. Mob stops to cast, conditions and GCD
```
AOEDOT:
  Cooldown: 1
  Conditions:
  - targetwithin 15
  - offgcd true
  Skills:
  - GCD{t=80}
  - message{m="$boss&e begins casting a spell"} @PIR{r=20}
  - potion{type=SLOW;d=80;level=7;} @self
  - delay 80
  - message{m="<target.name>&e is poisoned."} @PIR{r=20}
  - effect:particles{p=happyVillager;hs=1;vs=1;a=250;s=0.5;}
  - effect:sound{s=entity.spider.ambient;v=2;p=1;}
  - potion{type=POISON;d=200;level=1;} @PIR{r=10}
```
Single Target Lifetap
-------------------
* Basic
```
LifeTap:
  Cooldown: 1
  Skills:
  - effect:particles{p=dripLava;hs=1;vs=1;a=250;s=0.5;}
  - consume{d=12;h=12}
  - effect:particles{p=dripLava;hs=1;vs=1;a=250;s=0.1;} @self
```
* Advanced: Casting time, mob stops to cast
```
LifeTap:
  Cooldown: 1
  Skills:
  - message{msg="<mob.name>&e begins casting a spell."} @PIR{r=15}
  - potion{type=SLOW;d=30;level=7;} @self
  - delay 30
  - message{m="<target.name>&e feels their life drain away."} @PIR{r=20}
  - effect:particles{p=dripLava;hs=1;vs=1;a=250;s=0.5;}
  - consume{d=12;h=12}
  - effect:particles{p=dripLava;hs=1;vs=1;a=250;s=0.1;} @self
```
* Advanced: Casting time. Mob stops to cast, conditions and GCD
```
LifeTap:
  Cooldown: 1
  Conditions:
  - targetwithin 15
  - targetinlineofsight true
  - offgcd true
  Skills:
  - GCD 30
  - message{msg="<mob.name>&e begins casting a spell."} @PIR{r=15}
  - potion{type=SLOW;d=30;level=7;} @self
  - delay 30
  - message{m="<target.name>&e feels their life drain away."} @PIR{r=20}
  - effect:particles{p=dripLava;hs=1;vs=1;a=250;s=0.5;}
  - consume{d=12;h=12}
  - effect:particles{p=dripLava;hs=1;vs=1;a=250;s=0.1;} @self
```
Gravity Flux
--------------
* Launches player into air. * Advanced: casting time, mob stops to cast, conditions and GCD
```
GravityFlux:
  Cooldown: 30
  Conditions:
  - targetwithin 15
  - offgcd true
  Skills:
  - GCD{t=80}
  - message{msg="<mob.name>&e begins casting a spell."} @PIR{r=15}
  - potion{type=SLOW;d=40;level=7;} @self
  - delay 40
  - message{m="<target.name>&e rises chaotically into the air."} @PIR{r=20}
  - effect:sound{s=entity.wither.death;v=2;p=1;} @self
  - effect:particles{p=cloud:1:10:a=1000;s=0.01;}
  - throw{velocity=0;velocityY=10}
```
Meteor
----------
* Meteor v1 (Less CPU Intensive) * Advanced: Casting time. Mob stops to cast, conditions and GCD * Remember to specify this as an @target skill, eg. - skill{s=Meteor} @target
```
Meteor:
  Cooldown: 1
  Conditions:
  - targetwithin 15
  - targetinlineofsight true
  - offgcd true
  Skills:
  - GCD{t=60}
  - message{msg="<mob.name>&e begins casting a spell."} @PIR{r=15}
  - potion{type=SLOW;d=60;level=7;} @self
  - delay 60
  - message{m="&eA meteor slams into &f<target.name>."} @PIR{r=20}
  - effect:particles{p=cloud;vs=1;hs=1;a=50;s=0.01;y=20;}
  - effect:particles{p=reddust;vs=1;hs=1;a=100;s=0.01;y=20;}
  - delay 1
  - effect:particles{p=cloud;vs=1;hs=1;a=50;s=0.01;y=18;}
  - effect:particles{p=reddust;vs=1;hs=1;a=100;s=0.01;y=18;}
  - delay 1
  - effect:particles{p=cloud;vs=1;hs=1;a=50;s=0.01;y=16;}
  - effect:particles{p=reddust;vs=1;hs=1;a=100;s=0.01;y=16;}
  - delay 1
  - effect:particles{p=cloud;vs=1;hs=1;a=50;s=0.01;y=14;}
  - effect:particles{p=reddust;vs=1;hs=1;a=100;s=0.01;y=14;}
  - delay 1
  - effect:particles{p=cloud;vs=1;hs=1;a=50;s=0.01;y=12;}
  - effect:particles{p=reddust;vs=1;hs=1;a=100;s=0.01;y=12;}
  - delay 1
  - effect:particles{p=cloud;vs=1;hs=1;a=50;s=0.01;y=10;}
  - effect:particles{p=reddust;vs=1;hs=1;a=100;s=0.01;y=10;}
  - delay 1
  - effect:particles{p=cloud;vs=1;hs=1;a=50;s=0.01;y=8;}
  - effect:particles{p=reddust;vs=1;hs=1;a=100;s=0.01;y=8;}
  - delay 1
  - effect:particles{p=cloud;vs=1;hs=1;a=50;s=0.01;y=6;}
  - effect:particles{p=reddust;vs=1;hs=1;a=100;s=0.01;y=6;}
  - delay 1
  - effect:particles{p=cloud;vs=1;hs=1;a=50;s=0.01;y=4;}
  - effect:particles{p=reddust;vs=1;hs=1;a=100;s=0.01;y=4;}
  - delay 1
  - effect:particles{p=cloud;vs=1;hs=1;a=50;s=0.01;y=2;}
  - effect:particles{p=reddust;vs=1;hs=1;a=100;s=0.01;y=2}
  - delay 1
  - effect:particles{p=flame;vs=1;hs=3;a=1000;s=0.01;}
  - effect:particles{p=lava;vs=2;hs=1;a=100;s=1;}
  - effect:particles{p=lava;vs=1;hs=1;a=100;s=1;}
  - effect:particles{p=reddust;vs=1;hs=3;a=500;s=0.01;}
  - effect:sound{s=entity.ghast.fireball;v=1;p=1;}
  - throw{velocity=3;velocityY=3}
  - potion{type=slow,duration=20;level=7;}
  - damage{a=6;ignorearmor=true;}
```
* Meteor v2 (More CPU intensive) * Advanced: Casting time. Mob stops to cast, conditions and GCD
```
Meteor:
  Cooldown: 1
  Conditions:
  - targetwithin 15
  - targetinlineofsight true
  - offgcd true
  Skills:
  - GCD{t=60}
  - message{msg="<mob.name>&e begins casting a spell."} @PIR{r=15}
  - potion{type=SLOW;d=60;level=7;} @self
  - delay 60
  - message{m="&eA meteor slams into &f<target.name>."} @PIR{r=20}
  - effect:particles{p=lava;vs=1;hs=1;a=300;s=1;y=20;}
  - delay 1
  - effect:particles{p=lava;vs=1;hs=1;a=300;s=1;y=18;}
  - delay 1
  - effect:particles{p=lava;vs=1;hs=1;a=300;s=1;y=16;}
  - delay 1
  - effect:particles{p=lava;vs=1;hs=1;a=300;s=1;y=14;}
  - delay 1
  - effect:particles{p=lava;vs=1;hs=1;a=300;s=1;y=12;}
  - delay 1
  - effect:particles{p=lava;vs=1;hs=1;a=300;s=1;y=10;}
  - delay 1
  - effect:particles{p=lava;vs=1;hs=1;a=300;s=1;y=8;}
  - delay 1
  - effect:particles{p=lava;vs=1;hs=1;a=300;s=1;y=6;}
  - delay 1
  - effect:particles{p=lava;vs=1;hs=1;a=300;s=1;y=4;}
  - delay 1
  - effect:particles{p=lava;vs=1;hs=1;a=300;s=1;y=2;}
  - delay 1
  - effect:particles{p=flame;vs=1;hs=3;a=1000;s=0.01;}
  - effect:particles{p=lava;vs=1;hs=1;a=1000;s=1;}
  - effect:particles{p=cloud;vs=1;hs=3;a=1000;s=0.01;}
  - effect:sound{s=entity.ghast.fireball;v=2;p=1;}
  - throw{velocity=3;velocityY=3}
  - potion{type=slow,duration=20;level=7;}
  - damage{a=6;ignorearmor=true;}
```