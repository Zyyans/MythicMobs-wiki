**Description:** 

Before using this effect on live servers, make sure you know and understand exactly how it works. This effect in itself is already quite resource intensive and bad configurations of it can easily lead to extensive server lag and or crashes. Only use this effect if you're already experienced with using MythicMobs.

---

**Attributes:**

| Attribute        | Alias | Description                                                   | Default Value | Recommended Value |
| ---------------- | ----- | ------------------------------------------------------------- | ------------- | ----------------- |
| maxradius        | mr    | Max radius of the highest tornado “disk” shape                | 5             | 1                 |
| yoffset          | yo    | Does not actually affect anything                             | 0.8           | 0                 |
| height           | h     | # of disks desired * 2 + 1 (Don't ask me why, it just works)  | 4             | 3                 |
| interval         | i     | How fast the particles vertically render. This can be experimented with “rotationspeed” as well. | 4 | 1 |
| duration         | d     | Duration of the effect in ticks                               | 200           | default           |
| rotationspeed    | rs    | How fast the particles will horizontally render. This can be experimented with “interval” as well. | 0.04 | 0.5 |
| sliceheight      | sh    | Any value below 1 will cause an incomplete tornado, while anything above 10 will cause different sized spheres to appear in a strange order. This has yet to be fully defined | 64 | 1 |
| cloudparticle    | cp    | The particle type at the base of the tornado. Typically something like the “impact” as a tornado spins around, hence the largeexplode example. | largeexplode | largeexplode |
| cloudsize        | cs    | The radius of the cloud's particle appearances. (Kind of like sphere) | 5     | 1                 |
| cloudamount      | ca    | How many particles will appear at each randomly generated cloud location. | 1 | 1                 |
| cloudhspread     | chs   | The horizontal spreading of the cloud.                        | 1             | 1                 |
| cloudvspread     | cvs   | The vertical spreading of the cloud.                          | 1.8           | 0.1               |
| cloudpspeed      | cps   | Speed of the playing of the cloud particles                   | 2             | default           |
| cloudyoffset     | cyo   | Y Offsetting of the entire tornado. (1 + your desired height) | 1.8           | 2                 |

---

**Examples:**

```
- effect:particletornado{p=flame;cp=largeexplode;mr=1;h=3;i=4;d=100;rs=1;sh=1;cs=0;ca=0;chs=0.1;cvs=0.1;cps=1;cyo=2} @self ~onTimer:100
```