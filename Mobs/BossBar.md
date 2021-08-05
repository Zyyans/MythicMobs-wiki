**BossBar**

The BossBar feature is used to give your custom bosses a healthbar in the same style used by the Ender Dragon and Wither plus a bunch of customization options.

**Syntax**

```
internal_mobname:
  Type: <mobtype>
  BossBar:
    Enabled: [true/false]
    Title: '[name]'
    Range: [range]
    Color: [color]
    Style: [style]
    CreateFog: [true/false]
    DarkenSky: [true/false]
    PlayMusic: [true/false]
```

Available colors for Color (case sensitive): PINK, BLUE, RED, GREEN, YELLOW, PURPLE, WHITE

Available styles for Style (case sensitive): SOLID, SEGMENTED_6, SEGMENTED_10, SEGMENTED_12, SEGMENTED_20

Range is the distance the BossBar will be displayed to players around the mob

CreateFog, DarkenSky, and PlayMusic are buggy and do not currently work as of 2.5.0

**Examples**

Test:

```
SuperCreeper:
  Type: creeper
  Display: '&cTest'
  Health: 20
  BossBar:
    Enabled: true
    Title: 'Test'
    Range: 20
    Color: RED
    Style: SOLID
```