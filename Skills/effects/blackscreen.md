## Effect: Black Screen
----
Makes the player see with blindness.

### Attributes

| Attribute | Aliases |	Description | Default Value |
|--|--|--|--|
|duration|d|The time (in ticks) that the effect is active|20|

### Examples

Blinds players when the mob teleports

    BlackScreen:
      - blackscreen{d=2} @PlayersInRadius{r=100} ~onTeleport