**Description:** 

Creates a sphere of particles at the targeted entity or location. Extension of the [Particle Effect](/skills/effects/particles).

A list of particle types can be found [here](/skills/effects/particles/types).

---

**Attributes:**

This effect extends the general [Particle Effect](/skills/effects/particles) and uses all attributes from it.

| Attribute | Alias | Description                      | Default Value |
| --------  | ----- | -------------------------------- | ------------- |
| radius    | r     | The radius of the sphere to draw | 5             |

---

**Examples:**

```
- effect:particlesphere{particle=flame;amount=200;radius=5} @self
```