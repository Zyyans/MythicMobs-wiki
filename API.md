JavaDocs
--------

JavaDocs for MythicMobs API can be found here:

1.  <https://www.mythicmobs.net/javadocs/>

Maven
-----

### Repository

    <repository>
        <id>nexus</id>
        <name>Lumine Releases</name>
        <url>https://mvn.lumine.io/repository/maven-public/</url>
    </repository>

### Dependency

    <dependency>
        <groupId>io.lumine.xikage</groupId>
        <artifactId>MythicMobs</artifactId>
        <version>4.9.1</version>  
        <scope>provided</scope>
    </dependency>

Examples
--------

The MythicMobs API contains numerous events and helper classes to help
you utilize our mobs, items, and skill systems.

Some examples to help you get started can be found here:

1.  [MythicMobs API Examples
    Repo](https://github.com/xikage/MythicMobs-API-Examples)

Events
------

|                                                                  |                                                |
|------------------------------------------------------------------|------------------------------------------------|
| &lt; 100% 30% &gt;                                               |                                                |
| Event                                                            | Description                                    |
| [MythicReloadedEvent](/api/events/MythicReloadedEvent)           | Called when the plugin is reloaded             |
| [MythicMobSpawnEvent](/api/events/MythicMobSpawnEvent)           | Called when a MythicMob spawns                 |
| [MythicMobDeathEvent](/api/events/MythicMobDeathEvent)           | Called when a MythicMob dies                   |
| [MythicMobDespawnEvent](/api/events/MythicMobDespawnEvent)       | Called when a MythicMob despawns without dying |
| [MythicMobLootDropEvent](/api/events/MythicMobLootDropEvent)     | Called right before a loot table is generated  |
| [MythicConditionLoadEvent](/api/events/MythicConditionLoadEvent) | Called when a custom condition is loaded       |
| [MythicDropLoadEvent](/api/events/MythicDropLoadEvent)           | Called when a custom drop is loaded            |
| [MythicMechanicLoadEvent](/api/events/MythicMechanicLoadEvent)   | Called when a custom mechanic is loaded        |
| [MythicTargeterLoadEvent](/api/events/MythicTargeterLoadEvent)   | Called when a custom targeter is loaded        |
