**Description:** 

Plays a sound from either the vanilla game or a resource pack at the targeted entity or location. A good list of sounds can be found [here](https://minecraft.fandom.com/wiki/Sounds.json#Sound_events). Use the “sound event” column.

---

**Attributes:**

| Attribute        | Alias | Description                                                   | Default Values |
| ---------------- | ----- | ------------------------------------------------------------- | -------------- |
| sound            | s     | The sound to play                                             | NONE           |
| pitch            | p     | The pitch of the sound. Can be between 0.01 and 2.0           | 1.0            |
| volume           | v     | The volume of the sound.                                      | 1.0            |
| soundcategory    | sc    | The category at which the sound is played, useful for resourcepacks | NONE     |

The “volume” attribute doesn't define the percentage of the loudness of the sound, but rather determines how far (measured in blocks) the sound can be heard at maximum volume.

The formula for this is v * 16 = maxvolume distance. For example if you use “1” for the volume attribute, the sound can be heard at maximum volume in a radius of 16 blocks around the source. If you used “20” however, the sound can be heard at maximum volume in a 320 block radius! (20 * 16)

---

**Examples:**

```
- sound{s=entity.enderman.scream} @self
```