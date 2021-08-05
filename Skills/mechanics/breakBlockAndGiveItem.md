Mechanic: breakBlockAndGiveItem
===================================

Breaks the block at a target location and gives item(s). This mechanic will also drop the block (with exception of Bedrock). REQUIRES `forcesync=true`.

Attributes
--------------
| Attribute | Aliases   | Description                        | Default Value |
|-----------|-----------|------------------------------------|---------------|
| dodrops   | drops, d  | Whether or not to drop the block/s | true          |
| doeffect  | effect, e | Whether or not to play the break block particles (?) | true |
| usetool   | tool, t   | Whether or not to use the tool in the players hands (?) | true |
| fakelooting | fl | Plays the pickup-item animation from the origin | false |
| items | item, i | An array of item materials, or droptables. | |


Examples
--------

Using Crucible Items:

Instead of dropping dirt, it'll instead give diamonds to the player.
```yaml
#ITEMS FOLDER
CustomItem:
  Id: GOLDEN_SHOVEL
  Display: 'Lucky Shovel'
  Skills:
  - skill{s=dirtToDiamonds;sync=true} @TargetLocation ~onBreakBlock

#SKILLS FOLDER
dirtToDiamonds:
  TargetConditions:
  - blocktype{t=DIRT,GRASS_BLOCK} true
  Skills:
  - breakBlockAndGiveItem{dodrops=false;items=diamond}
```