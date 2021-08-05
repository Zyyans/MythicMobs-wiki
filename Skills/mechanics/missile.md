Mechanic: Missile
=================

*Added in version 2.2*

The missile skill is similar to the projectile skill. Missiles however
are homing and will track down their targets. The available syntax is
very similar to that of the projectile skill, too, but has some distinct
differences. Missiles cannot be summoned as the "METEOR"-type and cannot
hug the surface. However you can edit the inertia, add an onStart-skill
and specify wether or not the missiles can only hit their targets.

**Added in 4.10**

* Missiles can now target locations
* Added targetYoffset to missile mechanic

Attributes
----------

<table>
<thead>
<tr class="header">
<th>Attribute</th>
<th>Aliases</th>
<th>Description</th>
<th>Default Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Inertia</td>
<td>in</td>
<td><br />
Sets the "turning-rate" of the missile. Lower values make the missile turn around faster. Use big numbers (10-100) when trying to make your missiles turn slowly.</td>
<td>1.5</td>
</tr>
<tr class="even">
<td>onTick</td>
<td>oT</td>
<td>Meta-Skill executed every [interval] ticks at the projectile's origin location.</td>
<td>None</td>
</tr>
<tr class="odd">
<td>onHit</td>
<td>oH</td>
<td>Meta-Skill executed when the projectile hits something. Targets hit are inherited by the meta-skill.</td>
<td>None</td>
</tr>
<tr class="even">
<td>onEnd</td>
<td>oE</td>
<td>Meta-Skill executed when the projectile ends.</td>
<td><br />
None</td>
</tr>
<tr class="odd">
<td>onStart</td>
<td>oS</td>
<td>Meta-Skill executed when the projectile starts.</td>
<td>None</td>
</tr>
<tr class="even">
<td>Interval</td>
<td>i, int</td>
<td>How often (in ticks) the projectile update</td>
<td>4</td>
</tr>
<tr class="odd">
<td>HorizontalRadius</td>
<td>hRadius, hR, r</td>
<td>The horizontal radius entities will be hit in around the projectile.</td>
<td>1.25</td>
</tr>
<tr class="even">
<td>VerticalRadius</td>
<td>vRadius, vR</td>
<td>The vertical radius entities will be hit in around the projectile.</td>
<td>Horizontal Radius</td>
</tr>
<tr class="odd">
<td>MaxDuration</td>
<td>md</td>
<td>The max duration (in ticks) the projectile will persist.</td>
<td>100</td>
</tr>
<tr class="even">
<td>MaxRange</td>
<td>mr</td>
<td>The maximum range (in blocks) the projectile will travel.</td>
<td>40</td>
</tr>
<tr class="odd">
<td>Velocity</td>
<td>v</td>
<td>The velocity of the projectile</td>
<td>5</td>
</tr>
<tr class="even">
<td>StartYOffset</td>
<td>syo</td>
<td>Start Y Offset - Lets you offset where on the casting mob the projectile shoots from.</td>
<td>+1</td>
</tr>
<tr class="odd">
<td>StartFOffset</td>
<td>sfo</td>
<td>Start Forward Offset - How far in front of the mob the projectile starts</td>
<td>+1</td>
</tr>
<tr class="even">
<td>TargetYOffset</td>
<td>tyo</td>
<td>Target Y Offset - Lets you offset where on the target the projectile shoots at.</td>
<td>+1</td>
</tr>
<tr class="odd">
<td>HitPlayers</td>
<td>hp</td>
<td></td>
<td>true</td>
</tr>
<tr class="even">
<td>HitNonPlayers</td>
<td>hnp</td>
<td></td>
<td>false</td>
</tr>
<tr class="odd">
<td>HitTarget</td>
<td>ht</td>
<td></td>
<td>true</td>
</tr>
<tr class="even">
<td>HitTargetOnly</td>
<td></td>
<td></td>
<td>false</td>
</tr>
<tr class="odd">
<td>StopAtEntity</td>
<td>sE</td>
<td>Whether the projectile will stop upon hitting a targetable entity.</td>
<td>true</td>
</tr>
<tr class="even">
<td>StopAtBlock</td>
<td>sB</td>
<td>Whether the projectile will stop upon hitting an opaque block.</td>
<td>true</td>
</tr>
<tr class="odd">
<td>HugSurface</td>
<td>hs</td>
<td>Whether or not the projectile should move along the ground.</td>
<td>false</td>
</tr>
<tr class="even">
<td>PowerAffectsRange</td>
<td>par</td>
<td>Whether a mob's <a href="/skills/mechanics/power_level">power level</a> affects the projectile's range.</td>
<td>true</td>
</tr>
<tr class="odd">
<td>PowerAffectsVelocity</td>
<td>pav</td>
<td>Whether a mob's <a href="/skills/mechanics/power_level">power level</a> affects the projectile's velocity.</td>
<td>true</td>
</tr>
<tr class="even">
<td>fromOrigin</td>
<td>fo</td>
<td>Whether the missile should start from its origin</td>
<td>false</td>
</tr>
</tbody>
</table>

*"fromOrigin" was added in version 2.3*

Examples
--------

This example shoots a missile that looks like a thin trail of flames
with a high turning rate. It bursts into a powerful explosion upon
hitting its target.

    # Mob File
    Mob:
      Type: ZOMBIE
      Skills:
      - skill{s=Homer} @target ~onTimer:100

    # Skills File
    Homer:
      Skills:
      - missile{ot=Homer_TICK;oh=Homer_HIT;v=4;i=1;hR=1;vR=1;in=0.75}

    Homer_TICK:
      Skills:
      - effect:particles{p=flame;a=1} @origin

    Homer_HIT:
      Skills:
      - effect:particles{p=lava;a=50;hS=1;vS=1}
      - effect:sound{s=entity.generic.explode;v=1;p=0}
      - damage{a=1337;i=false}

  
