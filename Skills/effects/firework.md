Effect: Firework
----

Creates a firework effect at the target.
NOTE: Appears to not be working in Dev #3591, needs further testing.

### Attributes
----

| Attribute  | Aliases | Description | Default Value |
| ------ | ------ | ------ | ------ |
| type | t | The type of firework. See below for a list. | 0 |
| duration | d | The flight duration of the firework. | 0 |
| flicker | f | Whether to add the flicker effect to the explosion. | false |
| trail | tr | Whether to add the trail effect to the firework rocket. | false |
| colors | c | The color of the firework explosion, in RGB | 0,0,0 |
| fadecolors | fc | The fade colors of the firework explosion, in RBG | 0,0,0 |

#### Firework Types

The type attribute is given as a number, each number corresponds to the type of firework to use:
- 0 : Small Ball Explosion
- 1 : Large Ball Explosion
- 2 : Star Shaped Explosion
- 3 : Creeper-head Shaped Explosion
- 4 : Burst-style Explosion

### Examples
----
    Skills:
      - effect:firework{t=3;d=1;f=true;tr=true} @self ~onInteract
