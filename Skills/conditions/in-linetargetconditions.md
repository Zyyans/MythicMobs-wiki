**In-line Target Conditions (Premium Only!)**
=============================================

In-line target conditions allow you to apply conditions to your targeters so that you only target the exact entity / location you are looking for. First lets look at the formatting of it. 

In this example a mob would deal 1 damage to any players within 10 blocks that have the aura ``Plagued`` every second.
```
  Skills:
  - damage{a=1} @PIR{r=10;conditions=[  - hasaura{aura=Plagued} true ]} ~onTimer:20
```
The spacing is crucial for in-line target conditions. Notice that there is two spaces between ``conditions=[`` and ``- hasaura{aura=Plagued} true``. You need to have that double space there.
Also notice that there is one space from ``true`` to ``]}`` and that space needs to be there as well. it has something to do with yaml eating the last character of the inline condition, so without that space at the end, it would eat the ``e`` out of ``true`` and only output ``tru`` breaking the syntax.

Now that we understand the basics of it, lets look at an example that uses 2 in-line target conditions. There are 2 ways to do this. You can either drop down a line and indent, or you can keep them in the same line separating each condition by 2 spaces. 

Example of droping down a line and indenting:
```
  Skills:
  - damage{a=1} @PIR{r=10;conditions=[
                              - hasaura{aura=Plagued} false
                              - haspotioneffect{type=WITHER;d=1to999999;l=0to254} true 
                              ]} ~onTimer:20
```
Note that there is still a space after the true at the end of the second condition.

Example of keeping multiple conditions on one line:
```
  Skills:
  - damage{a=1} @PIR{r=10;conditions=[  - hasaura{aura=Plagued} true  - haspotioneffect{type=WITHER;d=1to999999;l=0to254} true ]} ~onTimer:20
```
Note that there is two spaces between ``conditions=[`` and the first condition, then there is also two spaces between the first condition and the second condition. Finally there is still one space after the true at the end of the second condition. 

These inline target conditions will work on every targeter that you use, anywhere you use the targeter, and almost every condition can be used inside of them as well. This includes conditions such as variableequals and variableisset. The next example we will go over how to use variableequals inside of an in-line target condition to only target an entity that has the correct variable set.

```
  Skills:
  - skill{s=LMG_ActivateAGreen} @MIR{r=50;
                                     t=LaserMinigameButtons;
                                     conditions=[
                                         - variableequals{var=target.myTeam;value="GREEN"} true
                                         - variableequals{var=target.amActive;value=0} true 
                                         ];
                                     limit=1;
                                     sort=RANDOM}
```
In this example we are inside of a meta-skill of a minigame. The targeter is checking all mobs of the type LaserMinigameButtons to see if they are on the green team, and checking that they are not activated. it is limited to 1 entity, and sorted randomly. You'll notice that since we are checking the target if its variables are equal to something, that we use the target scope inside the variableequals conditions. With this example, if will only ever select a LaserMinigameButton that has both the variable ``myTeam`` set to ``GREEN`` and the variable ``amActive`` set to ``0``. We can also set it up to be all in one line like mentioned above, and it would look like this: 
```
  Skills:
  - skill{s=LMG_ActivateAGreen} @MIR{r=50;t=LaserMinigameButtons;conditions=[  - variableequals{var=target.myTeam;value="GREEN"} true  - variableequals{var=target.amActive;value=0} true ];limit=1;sort=RANDOM}
```