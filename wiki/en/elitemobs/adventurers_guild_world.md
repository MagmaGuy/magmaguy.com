# Adventurer's Guild World

### What's the Adventure's Guild World?

The Adventurer's Guild World is the name of a premade world made for EliteMobs by Realm of Lotheridon.

![ag_pic_1.jpg](../../../img/wiki/ag_pic_1.jpg)

### What is the Adventurer's Guild World for?

The Adventurer's Guild World acts as a hub for EliteMobs. By hosting the hub, players no longer have to memorize any commands (other than /em) in order to interact with EliteMobs features.

In the world, the following NPCs are placed ahead of time:

- Transporter (for going back to your previous location)
- Guide (introductory quest to meet all NPC's)
- Guild Attendant (for upgrading [Guild Ranks]($language$/elitemobs/understanding_the_basics_of_elitemobs.md&section=step-2:-discovering-the-economy))
- Dungeon Teleporters (special NPC's that will teleport players to any installed [Dungeons]($language$/elitemobs/dungeons.md))
- Barkeep (currently unimplemented)
- Quest Giver (for browsing and accepting randomly generated quests)
- Blacksmith (for buying procedurally generated items and selling drops from elite mobs)
- Special Blacksmith (for buying custom items and selling drops from elite mobs)
- Combat Instructor (for giving tips about EliteMobs combat)
- Wormholes (portals that will teleport players to [Dungeons]($language$elitemobs/dungeons.md) and any other installed content)
- Arena Master (this NPC will let players participate in the [Wood League Arena]($language$elitemobs/understanding_the_basics_of_elitemobs.md&section=arenas))
- Story Mode Quests (let's players take quests for the [Story Mode Dungeons](www.magmaguy.com))
- Unbinder (let's players [Unbind]($language$/elitemobs/item_upgrade_system.md&section=unbinding-items) their EliteMobs loot for a price)
- Scrapper (let's players convert any unwanted loot to [Scrap]($language$/elitemobs/item_upgrade_system.md&section=scrapping-items))
- Repairman (players can interact with this NPC to [Repair]($language$/elitemobs/item_upgrade_system.md&section=repairing-elite-items) their items using scrap)
- Enchanter (let's players [Enchant]($language$/elitemobs/item_upgrade_system.md&section=enchanting-elite-items) their items)

Additionally, features an adventurer's guild building for the NPCs, as well as an EliteMobs Arena (currently unimplemented, coming soon!).

### How to set up the Adventurer's Guild World

To install the Adventurer's Guild World do the following:

1. Download the files. You can click on the red glass in `/em setup` to get links to the downloads.

2. Upload / move the files to your server's `/plugins/EliteMobs/imports` folder. Make sure you put the **ZIPPED** files inside the `imports` folder without modifying them in any way, EliteMobs will automatically extract the files and move them to the correct locations.

3. Restart or do `/em reload`. After a few seconds, when you do `/em setup` the indicators for the features you downloaded should be yellow.

4. Click on the yellow glass in the `/em setup` menu to install the imported features. If everything installed properly you should be in the Adventurer's Guild hub world. You can teleport to the Adventurer's Guild at any time by doing `/ag`.

#### Configuring The Wormhole

After installing the Adventurer's Guild hub world you will notice that there is a wormhole located where the players teleport in. This wormhole is supposed to be configured by you, to lead back to your regular world spawn or any other central location of your server.

To configure the wormhole, navigate to the directory *~plugins\EliteMobs\wormholes* and open *adventurers_guild_wormhole.yml*. Locate the `location2` value and replace `your_world_here` with the name of your world, followed by the correct coordinates where players should be teleported to.
