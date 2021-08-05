Mechanic: Feed
--------------

Feeds the targeted player.  
Doesn't work for other mobs.

### Attributes

| Attribute  | Aliases | Description                         | Default |
|------------|---------|-------------------------------------|---------|
| amount     | a       | The amount of hunger to restore     | 1       |
| saturation | s       | The amount of saturation to restore | 0       |
| overfeed   | o,of    | Whether or not to overfeed          | false   |

**Note:**  
1 amount is half a food unit.  
Overfeeding means excess food is converted into saturation.  
Allows for negative values to decrease food!

  

### Examples

This skill feeds the player 10 hunger (or 5 drumsticks).

    Skills:
    - feed{amount=10;} @trigger ~onInteract