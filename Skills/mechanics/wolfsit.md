Sets the sitting state of the target wolf.

**Attributes**

| Attribute | Alias | Description |
| --------- | ----- | ----------- |
| state     |       | The state the wolf is in. True = sitting and False = standing |

**Examples**

```
# Standing
- wolfSit{state=false} @self ~onInteract
```

```
# Sitting
- wolfSit{state=true} @self ~onInteract
```