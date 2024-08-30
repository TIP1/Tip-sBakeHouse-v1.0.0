# Tip's BakeHouse - Gamemode Framework v1.0.0

**Hey hey hey, welcome to my BakeHouse! ;)**

I'm excited to introduce my very first mod to you! I've worked on it for a long time, putting in a lot of effort to refine the concept and iron out any bugs that could interfere with your gameplay. It’s really important to me how you’ll feel after playing with my modification. Seriously...

## About

It all started on a summer Friday, a year ago. I came home in the evening wanting to play something other than online games with microtransactions and respawn waits, but there was nothing that interested me... Except for one game — **Arma 3**. However, I couldn't find a suitable mod or module for it (this was in 2023) that would allow me to create something similar to what Battlefield offers in terms of arcade-level intensity and frequency of battles. Instead, I had to come up with my own missions and so on. In short, I was constantly searching for something to keep myself entertained in this amazing game.

This highlighted a problem with **ALL** sandbox games — you end up working your brain instead of switching it off and enjoying the freedom, graphics, effects, and other players' mods.

After nearly 8-9 months, I realized there was no turning back — I had to finish what I started as a small script for my local scenarios. I became filled with enthusiasm, and it hasn't faded! I decided to create my own game! I also want to say that after 10 years of programming and all the time I spent meticulously writing this mod, I am deeply impressed by the work of **Bohemia Interactive**. I will definitely send them my resume to channel all my passion into working on **Arma 4**. I'm amazed by their approach to creating products, by never being afraid to start from scratch, to create their own tools, formats for images, and game engines. If someone has an idea in their head and can’t sleep peacefully because of it, they need to be brave enough to start a long and fruitful journey. Once they do, there’s no stopping them, and success is inevitable! Reading detailed documentation only fueled my energy further — thank you for supporting enthusiasts...

I’m just an **enthusiast**, for whom modding is just a hobby. As someone with experience in QA and development, I tried to make this mod as good as possible. If you find any bugs, I would greatly appreciate a bug report on the Discord server. In the future, I will definitely be doing a refactor for optimization and code readability. For now, I’ve decided to release my work because I can't leave it unfinished — I need to fully immerse myself in other tasks.

So... I present to you... A set of modules and some rules, which can be called a **framework** for changing the game’s gameplay. It can be easily expanded by adding new features and mechanics, modules, and scripts. That’s exactly what I’ll be working on in the future after some refactoring and bug fixing.

At this stage, it's more of an attempt to change the game’s gameplay, the emotions, and the experiences it gives you as a player. And I hope I’ve succeeded — I find myself spending hours in the editor while testing scenarios, the game has become more engaging without losing its excitement and emotions. My “**BakeHouse**,” as I would call my workshop, is like a home toy factory where I create things to help you get engrossed in the gameplay like a child and enjoy the game on a Friday evening.... :3

## Content:

So, in this version, let's call it v1.0.0, the following is included:

**Optimization Tools:**

1. Garbage Collector
2. Dynamic Simulation System

**Game Modes (Currently 2):**
1. Frontline Mode
2. Capture the Flag Mode

**Various Modules that Might be Useful:**

1. Spawner
2. Fog of War for Zeus
3. Unit Status Update Module

## Modules

Now, let’s go over the modules first. I won’t be writing descriptions for the parameters, because everything is already explained in the tooltips that appear when you hover over the parameters. I’ve tried to create as many customization options for your scenario as possible. If anything is unclear, feel free to ask questions on the project’s **Discord** server. I recommend experimenting with the module settings to create a **unique** scenario; there are so many that while testing the mod, I kept discovering something new due to the number of settings and their combinations. Sometimes this can even fix certain bugs!

**1. Garbage Collector**
 Removes dead bodies and destroyed vehicles.

**2. Dynamic Simulation System**
Allows you to play with stable FPS even when there are 2000-4000 units on one map, making it feel like you’re playing with only 200 units. Everything can be customized as you see fit.

**3. Frontline Mode**
We need to go into more detail here. This is a game mode for a **long global campaign**. The entire map is divided between two sides into sectors, and the side that captures all the sectors wins. In the future, I’ll refine the logistics and supply system. At this stage, troops will spawn in each frontline sector from your reserves. Keep in mind that sectors that are surrounded or deep in enemy territory will be unavailable for troop spawning. Everything can be customized or disabled as you like! :) To create a scenario with this game mode, you’ll need modules from the corresponding tab. All these modules have descriptions explaining their purpose.

**To create this scenario:**

I recommend playing as Zeus. To do this, place a character and a Game Master module, assign your character a variable name, and set them as the owner of the Game Master module. If you name the Game Master module something like "anywhatyouwant_dfc_zeus_anywhatyouwant_", you will get additional game options. It’s important that the name includes "**dfc_zeus**".

1. Place the **Frontline Map** module, it will create a game grid with sectors.

2. Place the **Frontline Flags** module, it is needed to change the sector status and also serves as a
	module that ends the game if necessary.

3. Place the **Frontline Logistic** modules, one for each side. After placing the Frontline Map, you can start the scenario and view the sector grid. Place these modules in sectors corresponding to each side; this sector will now be your logistics hub. Without it, units will spawn in surrounded sectors. **In version 1.0.0**, you only need 2 — one for each side.

4. Then place the **Frontline Spawn** modules wherever you like. All units within their radius will be considered spawning units for the corresponding side. You'll need 2 of these — one for each side.

5. After that, place the **Frontline Spawner** module. It will handle spawning units for the game.

6. Place the **Frontline Waypoints** module, which will create waypoints for the units.

7. If you want, you can place the **Frontline Waypoints for Zeus** module. It will provide waypoints when you directly control units as Zeus.

**4. Capture the Flag Mode**

This is a classic sector control gamemode.

**To create this scenario:**

I recommend playing as Zeus. Place a character and a Game Master module, assign your character a variable name, and set them as the owner of the Game Master module. If you name the Game Master module something like "anywhatyouwant_sc_zeus_anywhatyouwant_", you will get additional game options. It’s important that the name includes "**sc_zeus**".

1. Place the **Sector Map** module, which will create sectors in locations within its radius. You can place several of these modules. Alternatively, you can add your own sectors using the **Sector Flag** module.

2. Place the **Sector Flags** module, which is needed to change sector status and also serves as a module to end the game if necessary.

3. Then place the **Sector Spawn** module wherever you like. All units within its radius will be considered spawning units for the corresponding side. One per side. In this mode, there can be more than two sides.

4. After that, place the **Sector Spawner** module. It will handle spawning units for the game in sectors corresponding to each side.

5. Place the **Sector Waypoints** module, which will create waypoints for the units.

***The Frontline and Sector Control modes are compatible with each other!***

**5. Simple Spawner** - A classic spawner module suitable for any spawner tasks, it can also spawn units for a specific game mode (or for both). I recommend using it if, at the start of a Sector Control scenario, neither side has captured any flags (if all flags are neutral at the start of the game, units from the Sector Spawner will not spawn; Sector Spawner requires the corresponding owner for a sector, whereas Simple Spawner will spawn units at its location).

**6. Fog of War for Zeus** - You won’t see enemy units in Zeus mode.

**7. Unit Status Update Module** - Adds units to the curator-Zeus for editing, and also removes empty groups (from the scenario cache), allowing you to bypass the limit on the number of groups in the scenario.

**Supports any mods (may be buggy with AI-mods, but with Vcom works fine), any OS, any map. I didn't tested it in MP*

***With love, your Tip <3***

**@TipsBakeHouse**

[GITHUB](https://github.com/TIP1/Tip-sBakeHouse-v1.0.0)
[YOUTUBE](https://www.youtube.com/@TipTheBakerChannel)
[STEAM](https://steamcommunity.com/profiles/76561198130926199/)
[DISCORD](https://discord.gg/CuF55eWwhk)

  

**It is forbidden to reupload this mod on Steam Workshop*