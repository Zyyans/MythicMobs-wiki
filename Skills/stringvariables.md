Placeholders
------------

These are all of the placeholders and special characters you can use in
skills and mechanics that use strings.

##### Examples

This will make a mob (name in teal (&b)) send a message to all players
in a radius of 20 blocks around in itself, stating that it was slain by
player x (&lt;trigger.name&gt; in green (&a))

    Skills:
    - message{m="&b<mob.name>&r was slain by the warrior skills of &a<trigger.name>&r"} @PIR{r=20} ~onDeath

Skill Placeholders
------------------

<table>
<thead>
<tr class="header">
<th><strong>Mob Placeholder</strong></th>
<th><strong>Function</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>Some placeholders may not function properly if they don't apply to the caster (e.g. the caster is a player). Pre 4.6.0 versions use "mob" instead of "caster"</em></td>
<td></td>
</tr>
<tr class="even">
<td>&lt;caster.uuid&gt;</td>
<td>Returns the UUID of the caster</td>
</tr>
<tr class="odd">
<td>&lt;caster.level&gt;</td>
<td>Returns the level of the caster</td>
</tr>
<tr class="even">
<td>&lt;caster.name&gt;</td>
<td>Returns the name of the caster</td>
</tr>
<tr class="odd">
<td>&lt;caster.hp&gt;</td>
<td>Returns current hp of the caster</td>
</tr>
<tr class="even">
<td>&lt;caster.mhp&gt;</td>
<td>Returns the max hp of the caster</td>
</tr>
<tr class="odd">
<td>&lt;caster.php&gt;</td>
<td>Returns the percent hp of the caster</td>
</tr>
<tr class="even">
<td>&lt;caster.thp&gt;</td>
<td>Returns the full number hp of the caster</td>
</tr>
<tr class="odd">
<td>&lt;caster.tt.top&gt;</td>
<td>Returns the name of the top threat holder of the caster</td>
</tr>
<tr class="even">
<td>&lt;caster.l.w&gt;</td>
<td>Returns the world name the caster is in</td>
</tr>
<tr class="odd">
<td>&lt;caster.l.x&gt;</td>
<td>Returns the X coordinate of the caster</td>
</tr>
<tr class="even">
<td>&lt;caster.l.x.#&gt;</td>
<td>Returns the X coordinate of the caster<br />
+- random number between #</td>
</tr>
<tr class="odd">
<td>&lt;caster.l.y&gt;</td>
<td>Returns the Y coordinate of the caster</td>
</tr>
<tr class="even">
<td>&lt;caster.l.y.#&gt;</td>
<td>Returns the Y coordinate of the caster<br />
+- random number between #</td>
</tr>
<tr class="odd">
<td>&lt;caster.l.z&gt;</td>
<td>Returns the Z coordinate of the caster</td>
</tr>
<tr class="even">
<td>&lt;caster.l.z.#&gt;</td>
<td>Returns the Z coordinate of the caster<br />
+- random number between #</td>
</tr>
<tr class="odd">
<td>&lt;caster.l.yaw&gt;</td>
<td>Returns the yaw of the caster</td>
</tr>
<tr class="even">
<td>&lt;caster.l.pitch&gt;</td>
<td>Returns the pitch of the caster</td>
</tr>
<tr class="odd">
<td>&lt;caster.stance&gt;</td>
<td>Returns the current stance of the caster</td>
</tr>
<tr class="even">
<td>&lt;caster.owner.name&gt;</td>
<td>Returns the name of the wolf's owner</td>
</tr>
<tr class="odd">
<td>&lt;caster.owner.uuid&gt;</td>
<td>Returns the uuid of the wolf's owner</td>
</tr>
</tbody>
</table>

| **Variable Placeholders (v4.6)** | **Function**                                                            |
|----------------------------------|-------------------------------------------------------------------------|
| &lt;caster.var.\[name\]&gt;      | Returns the value of the variable \[name\] on the caster.               |
| &lt;skill.var.\[name\]&gt;       | Returns the value of the variable \[name\] on the current skill tree.   |
| &lt;skill.var.damage-amount&gt;  | Returns the amount of damage taken in the onDamaged trigger             |
| &lt;skill.var.damage-type&gt;    | Returns the type of damage taken as specified in a mechanic, aura, etc. |

<table>
<thead>
<tr class="header">
<th><strong>Target Placeholders</strong></th>
<th><strong>Function</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>These placeholders will return whatever targetselector has been used. For instance &lt;target.name&gt; + @NearestPlayer will return the name of the player closest to the casting mob.</em></td>
<td></td>
</tr>
<tr class="even">
<td>&lt;target.uuid&gt;</td>
<td>Returns the UUID of the target</td>
</tr>
<tr class="odd">
<td>&lt;target.name&gt;</td>
<td>Returns the name of the target</td>
</tr>
<tr class="even">
<td>&lt;target.hp&gt;</td>
<td>Returns the current hp of the target</td>
</tr>
<tr class="odd">
<td>&lt;target.threat&gt;</td>
<td>Returns the threat level of the target</td>
</tr>
<tr class="even">
<td>&lt;target.l.w&gt;</td>
<td>Returns the world name the target is in</td>
</tr>
<tr class="odd">
<td>&lt;target.l.x&gt;</td>
<td>Returns the X coordinate of the target</td>
</tr>
<tr class="even">
<td>&lt;target.l.x.#&gt;</td>
<td>Returns the X coordinate of the target<br />
+- random number between #</td>
</tr>
<tr class="odd">
<td>&lt;target.l.y&gt;</td>
<td>Returns the Y coordinate of the target</td>
</tr>
<tr class="even">
<td>&lt;target.l.y.#&gt;</td>
<td>Returns the Y coordinate of the target<br />
+- random number between #</td>
</tr>
<tr class="odd">
<td>&lt;target.l.z&gt;</td>
<td>Returns the Z coordinate of the target</td>
</tr>
<tr class="even">
<td>&lt;target.l.z.#&gt;</td>
<td>Returns the Z coordinate of the target<br />
+- random number between #</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th><strong>Trigger Placeholders</strong></th>
<th><strong>Function</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>&lt;trigger.uuid&gt;</td>
<td>Returns the UUID of the person triggering the skill</td>
</tr>
<tr class="even">
<td>&lt;trigger.name&gt;</td>
<td>Returns the name of the person triggering the skill</td>
</tr>
<tr class="odd">
<td>&lt;trigger.hp&gt;</td>
<td>Returns the current hp of the person triggering the skill</td>
</tr>
<tr class="even">
<td>&lt;trigger.threat&gt;</td>
<td>Returns the threat level of the person triggering the skill</td>
</tr>
<tr class="odd">
<td>&lt;trigger.l.w&gt;</td>
<td>Returns the world name of the person triggering the skill</td>
</tr>
<tr class="even">
<td>&lt;trigger.l.x&gt;</td>
<td>Returns the X coordinate of the person triggering the skill</td>
</tr>
<tr class="odd">
<td>&lt;trigger.l.x.#&gt;</td>
<td>Returns the X coordinate of the person triggering the skill<br />
+- random number between #</td>
</tr>
<tr class="even">
<td>&lt;trigger.l.y&gt;</td>
<td>Returns the Y coordinate of the person triggering the skill</td>
</tr>
<tr class="odd">
<td>&lt;trigger.l.y.#&gt;</td>
<td>Returns the Y coordinate of the person triggering the skill<br />
+- random number between #</td>
</tr>
<tr class="even">
<td>&lt;trigger.l.z&gt;</td>
<td>Returns the Z coordinate of the person triggering the skill</td>
</tr>
<tr class="odd">
<td>&lt;trigger.l.z.#&gt;</td>
<td>Returns the Z coordinate of the person triggering the skill<br />
+- random number between #</td>
</tr>
</tbody>
</table>

  

Misc Placeholders
-----------------

| **Placeholder**       | **Function**                                        |
|-----------------------|-----------------------------------------------------|
| **Misc Placeholders** |                                                     |
| &lt;drops.xp&gt;      | Returns the xp dropped via Heroes or SkillAPI mods  |
| &lt;drops.money&gt;   | Returns the money dropped through the vault plug-in |

Special Placeholders
--------------------

| **Placeholder**                        | **Function**                                                              |
|----------------------------------------|---------------------------------------------------------------------------|
| &lt;caster.score.objective&gt;         | Returns the score of the caster from "objective" **(2.3)**                |
| &lt;target.score.objective&gt;         | Returns the targeters score from "objective" **(2.3)**                    |
| &lt;trigger.score.objective&gt;        | Returns the score of the trigger from "objective" **(2.3)**               |
| &lt;global.score.objective&gt;         | Returns the global score from "objective" **(2.3)**                       |
| &lt;score.objective.dummyname&gt;      | Returns the score of "dummyname" (fake player) from "objective" **(2.3)** |
| &lt;random.\#-\#&gt; <sup>(v4.6)</sup> | Returns a random number in the specified range                            |

Special Characters
------------------

| **Placeholder** | **Function**                          |
|-----------------|---------------------------------------|
| &lt;&co&gt;     | Returns a colon (:)                   |
| &lt;&sq&gt;     | Returns an apostrophe (')             |
| &lt;&da&gt;     | Returns a dash (-)                    |
| &lt;&bs&gt;     | Returns a backslash (\\)              |
| &lt;&fs&gt;     | Returns a forward slash (/)           |
| &lt;&sp&gt;     | Returns a space                       |
| &lt;&cm&gt;     | Returns a comma (,)                   |
| &lt;&sc&gt;     | Returns a semicolon (;)               |
| &lt;&eq&gt;     | Returns an equals symbol \[=\]        |
| &lt;&ss&gt;     | Returns a section symbol (§)          |
| &lt;&dq&gt;     | Returns double quotes (")             |
| &lt;&rb&gt;     | Returns a right bracket (\])          |
| &lt;&lb&gt;     | Returns a left bracket (\[)           |
| &lt;&rc&gt;     | Returns a right curly bracket (})     |
| &lt;&lc&gt;     | Returns a left curly bracket ({)      |
| &lt;&nl&gt;     | Forces a new line                     |
| &lt;&heart&gt;  | Returns a heart **(2.1.7)**           |
| &lt;&skull&gt;  | Returns a skull and bones **(2.1.7)** |

Color Codes
-----------

These color codes work anywhere in mob- and skill-files. They will even
properly format tellraw-commands used in command skills!

| **Code** | **Color**   | **Code** | **Color**      |
|----------|-------------|----------|----------------|
| &0       | Black       | &B       | Aqua           |
| &1       | Dark Blue   | &C       | Red            |
| &2       | Dark Green  | &D       | Light Purple   |
| &3       | Dark Aqua   | &E       | Yellow         |
| &4       | Dark Red    | &F       | White          |
| &5       | Dark Purple | &K       | Magic          |
| &6       | Gold        | &L       | Bold           |
| &7       | Gray        | &M       | Strike through |
| &8       | Dark Gray   | &N       | Underline      |
| &9       | Blue        | &O       | Italic         |
| &A       | Green       | &R       | Reset          |
