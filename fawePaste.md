Mechanic: fawePaste
===============

Pastes a Schematic using the FAWE Plugin found here: [FAWE](https://www.spigotmc.org/resources/fast-async-worldedit.13932/)

You must create a "Schematics" folder in your MythicMob directory and put the schematics you will use inside that folder.

Attributes
----------

| Attribute | Aliases | Description                                                   | Default Value |
|-----------|---------|---------------------------------------------------------------|---------------|
| schematic |  s       | Which schematic to load **from the MythicMobs Schematics folder**. | 1             |
| pasteAir | air,a       | Should air be pasted? | 1             |
| xOffset | x,xo      | The X offset of pasting the Schematic from the target.   | 0             |
| yOffset | y,yo      | The Y offset of pasting the Schematic from the target.   | 0             |
| zOffset | z,zo      | The Z offset of pasting the Schematic from the target.   | 0             |
| chestDropTable | chests,cdt      | Which MythicMob Drop Tables to supply the chests within the Schematic with.   | ""             |
| trappedchestDropTable | trapchests,tcdt      | Which MythicMob Drop Tables to supply the Trapped Chests within the Schematic with.   | ""             |

  

Examples
--------

  - fawePaste{schematic=deserttempleiron.schem;y=6;air=true;chestDropTable=IronDropTable} @origin
