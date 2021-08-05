Mechanic: Doppleganger
======================

Copies the appearance of the target player. Does nothing if the target
is not a player. This skill requires Libs' Disguises and ProtocolLib be
installed to enable disguise-functionality.

| Attribute     | Description                          |
|---------------|--------------------------------------|
| usePlayerName | Uses the player name as the new name |

Examples
--------

    Ditto:
      Type: SKELETON
      Skills:
      - doppleganger @NearestPlayer ~onSpawn
