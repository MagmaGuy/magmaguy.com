# Building for EliteMobs

The following wiki page helps you understand the process required to create EliteMobs dungeons and arenas.

Vocabulary:

- "Boss" - Big encounter, meant to be fought by a lot of people
- "Miniboss" - Smaller encounter, usually able to be killed by 1 player
- "Fodder" - Relatively easy mobs to kill

## Understanding the EliteMobs dungeon categories

### Lairs

Smallest size category

Lairs are usually 50x50 single-build structures, distributed as worlds, and usually contain one big boss encounter, though some can also contain a miniboss and some fodder.

### Minidungeons

Medium size category

Minidungeons are closer to 100x100 or 150x150 structures, often times with several structures or structures with several sections. These have 1 boss, and usually at least 3 or more minibosses. They also have lots of fodder.

### Adventures

Adventures are whole adventure maps, usually not measured in blocks. These are city-sized or even larger. They have 1 boss and 10+ minibosses, and dozens of unique fodder which usually amounts to hundreds or thousands in total in the map.

### Arenas

Arenas are wave-based survival arena challenges in EliteMobs. These are usually 100x100. They can have any amount of waves, but it's not usually recommended going over 50.

### Instanced Dungeons

Instanced Dungeons are similar to Minidungeons except that they are instanced. Meaning that every time a player or a group of players wishes to go to an Instanced Dungeon a new world is generated just for them.

Instanced Dungeons behave a lot like instanced dungeons that you might find in your favorite MMO. They usually have three difficulty levels with the rewards being better the harder the difficulty gets. They let players assume the roles of a Tank or DPS by equipping loot that is dropped within the instanced dungeon. Mobs will also use different sets of powers depending on what difficulty was picked when the players launched the instance. Any mobs that get slain in an instance will not respawn for the duration of that instance.

Any loot that is dropped within an instanced dungeon uses the greed or need system, meaning that the players can vote on the dropped item. As mentioned previously, instanced dungeon loot is specially made to be either defense oriented (tank) or offense oriented (DPS).

### Raids

Instanced content - coming soon

## Theming

The most important thing about any EliteMobs structure is the theme. Themes influence design of the build, its contents, its lore and its bosses.

As an example, you can see [The North Pole here](https://magmaguy.itch.io/elitemobs-the-north-pole). It had the concept of putting Christmas-related bosses in a snowglobe, resulting in a visually striking and mechanically interesting location.

Here is an other example, [The Oasis](https://magmaguy.itch.io/elitemobs-oasis). This was all about making an ancient Egypt location overrun with the undead and mummies, and it is one of the most popular builds in EliteMobs.

## Combat locations

Combat locations should avoid creating terrain which is easily exploitable. This means avoiding making pillars players can climb on to be safe, decorations that can be used to cheese the AI and other such obstacles. Some exploits are always going to be found, and that's not too important, but boss locations should be less prone to suffer from these exploits.

The ideal boss combat area is relatively flat, unobstructed, around 30 blocks in radius and can contain some pillars or other map elements which players must hide behind to clear certain boss mechanics.

Corridors should aim to be at least 5 blocks wide if they are meant to have adds in them. Miniboss arenas can be 15ish blocks in radius, depending on the powers/theming they have.

Please note that these are minimum dimensions. There's not really any problem if you go over.

Keep in mind that you can seal off or change the environment blocks either using [EliteScript]($language$/elitemobs/elitescript_actions.md&section=place_block) or [Transitive Blocks]($language$elitemobs/creating_world_bosses.md&section=onspawnblockstates-and-onremoveblockstates). This is a great way to make sure players can only progress further once they have defeated a certain mob.

## Designing for EliteMobs

The better you know EliteMobs, the better the content you make for it will be. The following is a list of EliteMobs features which will help you come up with interesting things for your dungeon:

- [Regional Bosses]($language$/elitemobs/creating_world_bosses.md) - Every creature in Dungeons is a regional boss, meaning that they have a leash (if they go over a certain distance they get pulled back to their spawn point) and respawn on a timer.
- [Creating bosses]($language$/elitemobs/creating_bosses.md) This will show you everything a boss can do and be, like disguises, health multipliers, whether it can move and at what speed, taunts & more!
- [EliteScript]($language$/elitemobs/creating_powers.md) EliteScript is the most powerful tool at your disposal when it comes to creating unforgettable encounters where only your imagination is the limit.
- [Treasure Chests]($language$/elitemobs/creating_treasure_chests.md) These can have items or even turn into enemies
- [Boss phases]($language$/elitemobs/creating_boss_phases.md) - Bosses can have phases. This system is very powerful because bosses can turn into anything between phases, including different entity types, different disguises, different custom models and so on.
- [Transitive Blocks]($language$/elitemobs/creating_world_bosses.md&section=onspawnblockstates-and-onremoveblockstates) These are blocks that get placed when a boss spawns or dies. They also can be spawned and cleared when a boss changes phases! These can be used to be make very interesting dynamic arenas.
- [Wormholes]($language$/elitemobs/creating_wormholes.md) - cool portals that can teleport players to other locations.

## Encounter design

Encounter design should be a priority when designing the combat area. Ideally you would have an idea of which powers you want to use, or at least of what theme of the powers should be - something like fire, or lighting, or ice, or reinforcements, or anything else that fits with the EliteMobs powers. Once you know what you want the powers to be, you can design the combat area accordingly.

If the bosses have a power that required running away from them, the area needs to be big enough to accommodate that. If there is a power where you must hide behind an obstacle, the structure needs that kind of obstacle. There's a lot of details that can go into building these arenas, and the more you take into account the better the encounter will be.

## Modifying the EliteMobs Resource Pack

As of Minecraft version 1.21.4 and EliteMobs version 9.1.13, the EliteMobs resource pack has been updated to align with Minecraft's new method for using custom models.  

The updated EliteMobs resource pack structure is as follows:  

**elitemobs_resource_pack**  
- **assets**  
  - **elitemobs**  
    - **items**  
      - This directory contains JSON files that define which custom models Minecraft can use. The actual models are stored in the `models` folder.  
      - Subdirectories:  
        - **coins**  
        - **equipment**  
        - **primis_map**  
        - **ui**  
    - **models**  
      - This folder contains the actual model files as JSON files.  
      - Subdirectories:  
        - **coins**  
        - **equipment**  
        - **primis_map**  
        - **ui**  
    - **textures**  
      - This folder stores all textures, including those used by the models.  
      - Subdirectories:  
        - **blocks**  
        - **gui**  
        - **items** (this is where model-specific textures are stored)  
        - **primis_map**  
        - **ui**  
  - **minecraft**  
    - **atlases**  
    - **font**  
    - **models**  
      - **items** (contains JSON files that specify which items in Minecraft should use custom models)  
    - **sounds**  
      - **custom** (stores custom sound files)

---

Let's break down how a JSON file in the *.minecraft\resourcepacks\elitemobs_resource_pack\assets\elitemobs\items\coins\* folder is structured and what it does:

```
{
  "model": {
    "type": "minecraft:model",
    "model": "elitemobs:coins/coin1"
  }
}
```

Purpose:
This JSON file tells Minecraft that this is a model, specifies the type of model, and indicates the location of the model file.

Key Fields:

`type: minecraft:model`
This specifies that the file represents a model type.
`model: elitemobs:coins/coin1`
This points to the location of the model within the resource pack.

Path Details:

`elitemobs:` instructs Minecraft to look in the elitemobs folder within the assets directory.
`coins/coin1` specifies the subfolder and the model file name.

The full path to the referenced model file is:
`*.minecraft\resourcepacks\elitemobs_resource_pack\assets\elitemobs\models\coins\coin1.json`

---

A good way to test if your custom models are working correctly is to use the following command:

/minecraft:give @p apple[item_model="elitemobs:coins/coin1"]

How It Works:
This command gives you an apple that uses the `elitemobs:coins/coin1` model. If the resource pack is set up correctly, you should see the custom coin model applied to the apple item.


Testing Your Own Custom Model:
If you’ve added your own custom model to the resource pack, follow these steps to test it:

1. **Create the Model JSON**:  
   Place your JSON file in the appropriate subfolder within the `items` directory.  
   For example:  
   `assets/elitemobs/items/mymodel/myawesomemodel.json`

2. **Add the Model File**:  
   Add the corresponding model file (`myawesomemodel.json`) to the `models` folder within the same subfolder.  
   For example:  
   `assets/elitemobs/models/mymodel/myawesomemodel.json`

3. **Add the Texture**:  
   Add the texture file for the model in the `textures` folder.  
   For example:  
   `assets/elitemobs/textures/items/myawesomemodel.png`

---

Once everything is set up, use the command below to test your model:

`/minecraft:give @p apple[item_model="elitemobs:mymodel/myawesomemodel"]`

If everything was done correctly, you’ll receive an apple in your hand, and it will display your custom model instead of the default apple model.




## Questions?

[Ask on discord any time!](https://discord.gg/9f5QSka)
