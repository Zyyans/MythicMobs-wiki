Mechanic: Weather
=================

Changes the weather in the casting mob's world.

Attributes
----------

| Attribute | Aliases   | Description                                               | Default |
|-----------|-----------|-----------------------------------------------------------|---------|
| type      | sunny [1] | The type of weather. Can be "sunny", "rainy", or "stormy" | sunny   |
| duration  |           | How long (in ticks) the weather will be forced to last    | 500     |

  
Aliases for weather types:  
|**Sunny**| sun, clear|

|            |                |
|------------|----------------|
| **Rainy**  | rain           |
| **Stormy** | storm, thunder |

Examples
--------

Causes a storm for 10 minutes when the mob spawns.

      Skills:
      - weather{type=storm;duration=6000} ~onSpawn

[1] ????
