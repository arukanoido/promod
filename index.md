---
layout: default
title: Home
---

Squad ProMod comes from an effort to rebalance Squad's meta for competitive play, with additional features to help casters make their streams more dynamic and informative.

# <a name="balance">Balance</a>
Rather than configuring gameplay mechanics within the Squad modding tools to one-size-fits-all values, we have exposed values for customization by event coordinators. These values can be modified via config files stored within the mod folder or ingame via a custom UI. 

<a href="https://i.imgur.com/FOHe1jo.png" target="_blank" rel="noopener noreferrer">![main menu mod settings](https://i.imgur.com/L6DKtpA.png)</a>

A mod settings menu is provided for configuring mod features. This mod settings menu is designed as a modular system which can be dropped into other mods and used quickly. As the mod is open source, we encourage you to use this mod settings module in your mods. See <a href="#modsource">Mod Source</a> for the link to the mod's source package. See the [Settings Tutorial](https://arukanoido.github.io/swc-mod/settings-tutorial) for detailed instructions.

# <a name="casters">Casting Features</a>
All of the following features are only available to users in Admin Cam.

<a href="http://www.fissureentertainment.com/devilsd/UnrealEngine/SWCMod/Images/SquadListOverview.png" target="_blank">![edit panel](https://i.imgur.com/ehgWzeE.png)

### Flag status 
A persistent display at the top of the screen showing the AAS lattice and the team owning each flag.

### Kill & Event feed
A persistent feed in a panel at the top right which shows infantry kills as they happen, as well as FOB, HAB, or vehicle destruction.

### Event point of interest icons
When a FOB, HAB, vehicle, or flag event occurs, an icon is placed above the event in the game world showing what type of event occurred. The `R` key will automatically move the camera to the event's location so that casters can quickly react to events as they happen. The `T` key returns the camera to the original location.

<a href="http://www.fissureentertainment.com/devilsd/UnrealEngine/SWCMod/Images/POIOverview.png" target="_blank">![edit panel](https://i.imgur.com/A2psYjN.png)

### Map Teleport
You can select a place on the map to instantly go to by double clicking on it. 

### Follow camera
When you target a player or a vehicle, you will see a red triangle indicating that they can be followed. Pressing `Left Mouse Button` will attach the camera to them, so that as they move, the camera moves. While in follow mode, you can't move the camera with WASD, only look around. Pressing `Left Mouse Button` again will toggle the mode off.

### Spectate camera
When you target a player, pressing `Right Mouse Button` will open a small window in the bottom left, showing that player's viewpoint. Pressing `Q` will toggle the window size to be larger or smaller. Pressing `E` will replace the main view with the player's viewpoint entirely. `Right Mouse Button` will toggle the mode on and off.

<a href="http://www.fissureentertainment.com/devilsd/UnrealEngine/SWCMod/Images/CastingFeatureOverview.png" target="_blank">![overview](https://i.imgur.com/1l1tuGh.png)</a>

# <a name="config">Configuration</a>

Game
 - Startup time (in seconds)
 - Match time (in seconds)
 - Time between rounds (in seconds)

Layer
 - Starting ticket amount (per team)

Vehicles
 - Ticket cost
 - Respawn time (in seconds)
 
Flags
 - Tickets lost on flag capture
 - Tickets gained on flag capture
 - Gain tickets from neutral
 - Tickets gained on neutral capture

# <a name="known-issues">Known Issues</a>

1. White screen loading a map
> Normal behavior when loading any mod maps.
2. Cannot use Admin console commands when switching from a vanilla map to a mod map
> A vanilla Squad bug. Reconnect to the server after changing the map.
3. Stuttering in the Spectate Camera using in-picture mode.
> An engine optimization. Keep the spectated player in view on your screen when using in-picture mode.

# <a name="credit">Credit</a>
<dl>
 <dt>salt. DevilsD</dt>
 <dd>Discord: DevilsD#0613</dd>
</dl>

<dl>
 <dt>|F| Arkanoid</dt>
</dl>

# <a name="modsource">Mod Source</a>
We are making the mod SDK files available as a modder's resource. Usage is free for non-commercial purposes. The credit section of this page should be included wherever the mod is used. Contact DevilsD via Discord if you have technical questions or questions about usage.

<a href="http://www.fissureentertainment.com/devilsd/UnrealEngine/SWCMod/Source" target="_blank">Download here.</a>

---
