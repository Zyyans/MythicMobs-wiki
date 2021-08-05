**Description:** Matches the last signal received by the target mob

**Type:** Entity

---

**Attributes:**

| Attribute | Alias | Description         |
| --------- | ----- | ------------------- |
| signal    | s     | The signal to match |

---

**Examples:**

```
Conditions:
- lastsignal{s=fireCannonShot} true
```