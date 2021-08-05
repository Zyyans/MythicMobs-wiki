Mechanic: Summon
================

Summons mobs of the given type around the target.

Attributes
----------

| Attribute          | Aliases | Description                                                                                                                                  | Default Value |
|--------------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| type               | t       | The type of mob to summon. Can be a Mythic Mob type or a regular entity type.                                                                | SKELETON      |
| amount             | a       | The number of mobs to summon.                                                                                                                | 1             |
| level              | l       | The level of the mob being summoned.                                                                                                         | 0             |
| radius             | r       | The radius around the target within which the mobs will be summoned.                                                                         | 0             |
| yRadius            | yr      | Overrides the Y component of radius.                                                                                                         | radius        |
| yRadiusUpOnly      | yu      | (true/false) Whether the Y spread should only go upward, not downward.                                                                       | false         |
| onSurface          | os      | (true/false) Whether the mobs should be spawned only on a solid block                                                                        | true          |
| copyThreatTable    | ctt     | Whether the summoned mobs should copy the parent's threat table. Requires threat tables to be enabled on the summoned mob to function.       | false         |
| inheritThreatTable | itt     | Whether the summoned mobs should share a threat table with the parent. Requires threat tables to be enabled on the summoned mob to function. |               |
| inheritFaction     | if      | Whether the summoned mobs should have the same faction as the parent.                                                                        |               |
| summonerIsOwner | sio | Whether to set the summoner as the owner of the mob. | true |
| summonerIsParent | sip | Whether to set the summoner as the parent of the mob. | true |

  

Examples
--------

This example would summon 5 wither skeletons around the target players.

    RaiseSkeletons:
      Skills:
      - summon{type=WITHER_SKELETON;amount=5;radius=4} @PIR{r=20}