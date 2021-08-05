Commands
========

Mythic Mobs has a simple command structure that can be accessed by typing **/mythicmobs**. Typing that will display a menu with all available commands, and each level of commands will provide menus or information about what you can do. All command parameters surrounded by []'s are required, while &lt;&gt;'s are optional.

General Commands
----------------

-    **/mm** (alias: **/mythicmobs**) *Base command for the plugin. Displays all other commands.*
-    **/mm debug [level]** (alias: **/mm d [level]** *Sets the plugin's debug level. 0 = OFF.*
-    **/mm debugmode [true/false]** *Enables debug mode, which disables random spawners, mob spawners, and other random things that make debugging difficult.*
-    **/mm reload** (alias: **/mm r**)  *Reloads the plugin.*
-    **/mm save** *Force saves all active mobs and spawners.*
-    **/mm version** *Displays MythicMobs version.*

Item Commands
-------------

-    **/mm items** (alias: **/mm i**)  *Base for all item related commands.*
-    **/mm items get [item_name] &lt;amount&gt;** *Gives yourself an item from the configured mob equipment.*
-    **/mm items give [player] [item_name] &lt;amount&gt;**  *Gives a player an item from the configured mob equipment.*
-    **/mm items give -s [player] [item_name] &lt;amount&gt;**  *Silently gives a player an item from the configured mob equipment.*
-    **/mm items list** * *Lists off all configured mob equipment.*
-    **/mm item import &lt;itemName&gt; [fileName]** * *Imports held item to the Items folder. (File name defaults to &lt;itemName&gt;.yml)*

Mob Commands
------------

-    **/mm mobs** (alias: **/mm m**) *Base for all mob related commands.*
-    **/mm mobs info [mob_name]** *Displays lots of information about a Mythic Mob.*
-    **/mm mobs list** *Displays a list of mobs loaded to the server.*
-    **/mm mobs listactive** *Displays a list of currently spawned mobs, and the number of each.*
-    **/mm mobs kill [mob_name]** *Removes all Mythic Mobs with  the provided name.*
-    **/mm mobs killall** *Removes all active Mythic Mobs.*
-    **/mm mobs killall -p** *Removes all persistent Mythic Mobs.*
-    **/mm mobs spawn [mob_name]:&lt;level&gt; &lt;amount&gt; &lt;world,x,y,z&gt;** *Spawns mobs with the provided name.*
-    **/mm mobs spawn -s [mob_name]:&lt;level&gt; &lt;amount&gt; &lt;world,x,y,z&gt;** *Silently spawns the mob in- no console text.*
-    **/mm mobs stats** *Displays useful information about how many mobs are loaded on the server. (Amounts)*

Mob Egg Commands
----------------

-    **/mm egg** (alias: **/mm e**) *Base for all egg related commands.*
-    **/mm egg get [mob_name] &lt;amount&gt;** *Gives you mob eggs for the specified Mythic Mob.*
-    **/mm egg give [player] [mob_name] &lt;amount&gt;** *Gives a player mob eggs for the specified Mythic Mob.*

Spawner Commands
----------------

-   Mob spawners can use special filters and wild cards in most commands in place of the spawner's name to run the command on multiple spawners.
-   Use **g:group_name** to run commands on a whole group of spawners.
-   Use **r:radius** to run commands on all spawners within **radius** blocks
-   Use **?** for a single-character wildcard: Running the command **/mm s set ?at leashrange 32** will set it on spawners named Cat, Rat, Fat, but not one named Matt.
-   Use ***** for any number of wildcard characters: Running the command **/mm s set T* leashrange 32** will set the leash range to 32 on all spawners starting with T
-   **Running the command using \* for the spawner name will change ALL spawners**
-   **/mm spawners** (alias: **/mm s**) *Base for all spawner related commands.*
-   **/mm s create** *[spawner_name]* *[mob name]*
    -   Creates a new spawner at the location of the players reticule.
    -   The spawner will spawner whatever mob_name you gave it which can be any internal minecraft mob or the name of a mob you created under the ExampleMobs.yml configuration page.
    -   **/mm s create Ruins_Skeleton1 DecayingSkeleton**
-   **/mm s set [spawner_name] [setting] [value]**
    -   Changes a setting of the spawner. See below for all settings
    -   See [Spawner Options Section](Spawners) for all the things that can be set here.
-   **/mm s addcondition [spawner_name] [condition] [value]**
    -   Adds a spawner condition which determines whether a mob should spawn when it's timer is up.
    -   See [Spawner Conditions](Databases/Spawners/Conditions) for conditions that can be applied here
-   **/mm s removecondition [spawner_name] [condition]**
    -   Removes a spawner condition.
    -   **/mm s removecondition Ruins_Skeleton1 outside**
-   **/mm s info [spawner_name]**
    -   Provides a list of information about a particular spawner.
    -   **/mm s info Ruins_Skeleton1** (Lists information about the Ruins_Skeleton1 spawner)
-   **/mm s listnear &lt;distance&gt;**
    -   Lists all spawners nearby.
    -   Add a the distance parameter to narrow the list down.
    -   **/mm s listnear 15** (Displays all the spawner names within 15 blocks)
-   **/mm s resettimers [name]**
    -   Resets cooldown and reset timers for the spawner listed.
-   **/mm s resettimers Ruins_Skeleton1** (Resets the Ruins_Skeleton1 spawner)
-   **/mm s activate [name]**
    -   Activates (forces a spawn from) a particular mob spawner.
-   **/mm s activate** Ruins_Skeleton1** (Spawns the Ruins_Skeleton1 spawner)
-   **/mm s cut [search_string]**
    -   Cuts a group of spawners according to a given string.
-   **/mm s cut g:BoneCastle** (Cuts all spawners in the "BoneCastle" spawner group)
-   **/mm s cut r:200** (Cuts all spawners in a 200 block radius)
-   **/mm s cut Elementals_** (Cuts all spawners whos name starts with Elementals_)
-   **/mm s cut** (Cuts all spawners. BE VERY CAREFUL!)
-   **/mm s paste**
    -   Pastes a group of cut spawners in a new relative location.
    -   Spawners can be pasted multiple times but it replaces previous pastes. (They are not duplicated)
-   **/mm s undo**
    -   Undoes the previous cut operation and puts them back where they were.
    -   Will only work if you have not yet cut a new group of spawners.

Utility Commands
----------------
- **/mm test cast [skillname]** - Allows you to run a skill as if you were a mob.
-  **/mm i get [droptable]** - Allows you to get an item from a drop table as if you killed the mob dropping it.

Signal Commands
---------------

-   **/mm signal &lt;UUID&gt; &lt;signal&gt;**
    -   Used to signal mobs to toggle certain skills
    -   Only works when used with the mobs UUID, doesnt work with
        mobnames
    -   Usually used as a tellraw-command component
    -   This command is available to all players. However players cannot
        abuse this command unless they have the operator powers
        neccessary to find specific mob UUIDs and internal signal names
        of mobs.

Permissions
===========

At the moment MythicMobs only supports two permission nodes to grant
full access to the plugin. The reason for this is that nearly all
commands in MythicMobs are heavily abusable, and at the moment I don't
see a reason for individual permissions for each feature. Regardless, I
will add more permissions in the future when I have time for those that
would like it, but it is not high on my priority list.

General
-------

-   **mythicmobs.admin** - *Grants full access to the plugin's
    commands.*


Commands
--------

-   Access to individual commands can be given using
    **mythicmobs.command.&lt;command&gt;**

- **mythicmobs.command.info** - *Access to the **/mm info** command.*
- **mythicmobs.command.mobs.list** - *Access to the **/mm mobs list** command.*
- **mythicmobs.command.signal** - *Permission to use the "/mm signal
    &lt;mob.uuid&gt; &lt;signal&gt;" command*