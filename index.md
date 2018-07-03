---
layout: default
title: Home
---

The SWC mod comes from an effort to rebalance Squad's meta for competitive play, with additional features to help casters make their streams more dynamic and informative.

# <a name="balance">Balance</a>
Rather than configuring gameplay mechanics within the Squad modding tools to one-size-fits-all values, we have exposed values for customization by event coordinators. These values can be modified via config files stored within the mod folder or ingame via a custom UI. 

<a href="http://www.fissureentertainment.com/devilsd/UnrealEngine/SWCMod/ConfigEditorOverview.png" target="_blank">![edit ui](https://i.imgur.com/zornIpc.png)</a>

Configuration is only read from the server's mod folder, so players don't need to download configuration files. As with the rest of the mod's features, access to the ingame UI for editing config is limited to players with the Admin Cam role.

A full list of all exposed values is [available here](#config).

# <a name="casters">Casting Features</a>
All of the following features are only available to users in Admin Cam. These features can be toggled on or off with buttons in the spawn menu. 

<a href="http://www.fissureentertainment.com/devilsd/UnrealEngine/SWCMod/SquadListOverview.png" target="_blank">![edit panel](https://i.imgur.com/ehgWzeE.png)

### Flag status 
A persistent display at the top of the screen showing the AAS lattice and the team owning each flag.

### Kill & Event feed
A persistent feed in a panel at the top right which shows infantry kills as they happen, as well as FOB, HAB, or vehicle destruction.

### Event point of interest icons
When a FOB, HAB, vehicle, or flag capture event occurs, an icon is placed above the event in the game world showing what type of event occurred. The `Q` key will automatically move the camera to the event's location so that casters can quickly react to events as they happen. The `E` key returns the camera to the original location.

### Follow camera
When you target a player or a vehicle, you will see a red triangle indicating that they can be followed. Pressing `Left Mouse Button` will attach the camera to them, so that as they move, the camera moves. While in follow mode, you can't move the camera with WASD, only look around. Pressing `Left Mouse Button` again will toggle the mode off.


### Spectate camera
When you target a player, pressing `Right Mouse Button` will open a small window in the bottom left, showing that player's viewpoint. Pressing `Delete` will toggle the window size to be larger or smaller. Pressing `Insert` will replace the main view with the player's viewpoint entirely. `Right Mouse Button` will toggle the mode on and off.

<a href="http://www.fissureentertainment.com/devilsd/UnrealEngine/SWCMod/CastingFeatureOverview.png" target="_blank">![overview](https://i.imgur.com/1l1tuGh.png)</a>

# <a name="config">Configuration</a>

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

# <a name="credit">Credit</a>
<dl>
 <dt>salt. DevilsD</dt>
 <dd>Discord: DevilsD#0613</dd>
</dl>

<dl>
 <dt>|F| Arkanoid</dt>
</dl>
