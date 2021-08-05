Mechanic: togglesitting
=======================

**Aliases:** sit

Toggles the sitting state for cats, dogs, foxes, and parrots.

Attributes
----------

| Attribute | Aliases   | Description                        | Default Value |
|-----------|-----------|------------------------------------|---------------|
| setSitting | state    | Sets the sitting state             | false         |

Examples
--------
```
Dog:
  Type: Wolf
  Skills:
  - sit{state=true} @Self ~onInteract
```