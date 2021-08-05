**Description:** 

Creates a ring of particles around the targeted entity or location. Extension of the [Particle Effect](/skills/effects/particles).

A list of particle types can be found [here](/skills/effects/particles/types).

---

**Attributes:**

This effect extends the general [Particle Effect](/skills/effects/particles) and uses all attributes from it.

Particle attributes are “per point” in this effect, so keeping 'amount' low is recommended.

| Attribute       | Alias    | Description                                         | Default Value |
| --------------- | -------- | --------------------------------------------------- | ------------- |
| points          | p        | The number of points to draw representing the ring  | 10            |
| radius          | r        | The radius of the ring around the target            | 10            |

---

**Examples:**

Example would draw a ring of fire around the target consisting of 32 points.

```
- effect:particlering{particle=flame;radius=20;points=32;amount=1;hS=1;vS=0} @target
```