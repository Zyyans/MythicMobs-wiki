**Description:** Tests if the target has a scoreboard tag

**Type:** Entity

---

**Attributes:**

| Attribute | Alias   | Description          |
| --------- | ------- | -------------------- |
| tag       | t       | The tag to check for |

---

**Examples:**

```
Conditions:
- hastag{t=KilledBoss1} true
```

```
TargetConditions:
- hastag{t=PuzzleRoom1Solved} true
```