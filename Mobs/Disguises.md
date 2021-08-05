### Mob Disguises

**Mob disguises are dependent on the plugins [LibsDisguises ](https://www.spigotmc.org/resources/libs-disguises.81/)and [ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/). They will not work without both of those plugins. [The most up to date documentation for LibsDisguises can be found here](https://www.spigotmc.org/wiki/lib-s-disguises/)**

Most features do not require the premium version of LibsDisguises because LibraryAddict is a pretty nice dude.

**Note:** Some version of ProtocolLib work better than others- some versions break mob disguises, other players disguises, we do not have control over this. The LibsDisguises plugin will try to auto-update to a working version but sometimes that may fail. [check the discord if this is the case, normally we have backup links to working versions](mythicmobs.net/discord)

### Now that the technical mumbo-jumbo is over... What is a disguise?

Disguises allow you to make your mob look like a different mob, a block, or even an item! Disguises are great for shaking things up with mobs, allowing you to do things that are otherwise not possible… for example, making a spider that looks like a zombie– a zombie that climbs walls!. The possibilities are huge.

Any entity type found in the spigot docs should function correctly.
https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EntityType.html

### Options

All disguises have certain options available to them. These options go under the Disguises block, and can only be used in conjunction with a disguise (they will not work on their own). Some options will be mob specific. The lists of options for any entity can be found using `/dhelp <entity>`. Because this is generated by your plugin it should _always_ be up to date.

Here are some common ones that may be of interest to you:

- Disguise.Burning: true - Causes the mob to always appear to be burning
- Disguise.Blocking: true - Causes certain disguises to be stuck in the “blocking” animation.
- Disguise.Invisible: true - Makes the mob permanently invisible
- Disguise.Name: - Sets the disguised entity name
- Disguise.ShowName: true - Displays a nametag over certain disguises that would not normally have one (such as a block or item)
- Disguise.Sneaking: true - Causes certain disguises to be stuck in the “sneaking” animation.
- Disguise.Sprinting: true - Causes certain disguises to be stuck in the “sprinting” animation.
- Disguise.ModifyBoundingBox: false - Setting this to false will make mobs keep their original hitbox.
- Disguise.Glowing: [true/false] - Makes the disguise glow permanently.
- Disguise.Gliding: [true/false] - Makes the disguise glide permanently.

“Glowing” and “Gliding” were added in version 2.3.2.

Excessive Example:
```
SneakyDisguisingMob:
  Type: wither_skeleton
  Display: 'meh'
  CustomKillMessages:
  - '<target.name> was sneaked upon! (to death)'
  Health: 128
  Disguise:
    Type: player
    Skin: 'meeeh'
    Player: Steve
    Burning: true
    Blocking: true
    Invisible: false
    ShowName: false
    Sneaking: true
    Sprinting: true
    ModifyBoundingBox: false
    setDynamicName: true
```

#### Nameplates

Nameplates allow you to extend the nameplates of Player-disguise mobs, which are normally limited to 16 characters.
To use this, simply have Holograms installed and then leave out the “Player” field in your disguise (skin is still required!).
If you don't specify the player field, it will use the Display field instead using a custom nameplate.

```
Monkey:
  Type: skeleton
  Display: "this display name is too long for players normally"
  Disguise:
    Type: player
    Skin: Kurdie
```
This feature requires LibsDisguises and the Holograms plugin: [https://www.spigotmc.org/resources/holograms.4924/](https://www.spigotmc.org/resources/holograms.4924/)

If you have premium you can use multi line disguise names using the `setDynamicName` option

![image](uploads/e9f3926c7a8d74dfb1b8fa6d2cd2d67c/image.png)

#### Examples

Examples of Disguises being used:

```
MobType: skeleton
Disguise:
  Type: player
  Player: '&8Not Darkitect'
  Skin: Darkitect
```

```
MobType: skeleton
Health: 20
Disguise:
  Type: player
  Player: Ashijin
  Skin: Notch
```

```
MobType: skeleton
Health: 20
Disguise:
  Type: pig
```
You may also use in line conditions for the mobs disguise. For example from the skeleton shown earlier:
```
SLSkelF:
  Type: ZOMBIE
  Equipment:
  - IRON_SWORD HAND
  - SHIELD OFFHAND
  - LEATHER_HELMET HEAD
  - LEATHER_CHESTPLATE CHEST
  - LEATHER_LEGGINGS LEGS
  - LEATHER_BOOTS FEET
  Display: '&BSkeletal Fighter\n&ELv.<mob.level>'
  Disguise: SKELETON setDynamicName```
------------------------------------------------------------------------