Mechanic: Send Title
====================

Displays a "title" and/or "subtitle" message to all targeted players.
Does nothing if the target is not a player.

Attributes
----------

| Attribute | Aliases | Description                                            | Default Value |
|-----------|---------|--------------------------------------------------------|---------------|
| title     | t       | The title string to send. Must be in double-quotes.    | NONE          |
| subtitle  | st      | The subtitle string to send. Must be in double-quotes. | NONE          |
| duration  | d       | How long the title will display (in ticks)             | 1             |
| fadeIn    | fi      | The fade-in time for the title (in ticks)              | 1             |
| fadeOut   | fo      | The fade-out time for the title (in ticks)             | 1             |

  

Examples
--------

      Skills:
      - sendtitle{title="Beware!";subtitle="A dangerous spell is being cast!";d=20} @PlayersInRadius{r=10}
      - ...
