Mechanic: Toggle Lever
----------------------

Toggles a lever on and off at the supplied coordinates.

**Note:**  
The lever will switch back to the starting position after a set amount
of time. (Defaulting to 20 ticks/1 second).

Attributes
----------

| Attribute | Aliases | Description                                                 | Default Value |
|-----------|---------|-------------------------------------------------------------|---------------|
| duration  | d       | The duration (in ticks) the lever should remain toggled on. | 20            |
| x         |         | The X coordinate of the button.                             | 0             |
| y         |         | The Y coordinate of the button.                             | 0             |
| z         |         | The Z coordinate of the button.                             | 0             |

  

Examples
--------

    OpenSecretDoor:
      Skills:
      - togglelever{duration=600;x=15;y=67;z=-213}
