**Description:** 

Creates an puff of smoke at the location of the targeter.

---

**Attributes:**

| Attribute        | Alias | Description                                                   | Default Values |
| ---------------- | ----- | ------------------------------------------------------------- | -------------- |
| direction        | d     | The direction the effect should play towards. Can be 1-4.     | 1              |

---

**Examples:**

```
- effect:smoke @target ~onTimer:10
- effect:smoke{direction=2} @self ~onAttack
```