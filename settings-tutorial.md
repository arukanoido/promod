---
layout: default
title: Settings Tutorial
---

# Squad ProMod settings module tutorial

The settings component comes in 2 parts: the Config Parser, and the Mod Settings UI kit. The Mod Settings UI kit includes a component called BP_MainMenuModSettings which is added to the HUD and adds the MODS settings menu in the game's Main Menu.

1) Add BP_MainMenuModSettings component to your HUD class override.

<a href="https://i.imgur.com/FOHe1jo.png" target="_blank" rel="noopener noreferrer">![main menu mod settings](https://i.imgur.com/L6DKtpA.png)</a>

For settings to be persisted to disk on the client or server, BP_SettingsPlayerState and BP_SettingsGameState overrides are provided which include the necessary RPCs for managing read and write. These overrides should be placed last in the reference chain. If you already have overrides for PlayerState and GameState classes, reparent BP_SettingsPlayerState to BP_YourPlayerState class (and the same for BP_SettingsGameState) or if not, reparent BP_SettingsPlayerState to Squad's default classes, called SQPlayerState and BP_GameStateSquad respectively.

2) Reparent BP_SettingsPlayerState and BP_SettingsGameState as the child of any existing PlayerState or GameState classes, and set them as overrides in your GameMode class.

![reference tree](https://i.imgur.com/42rI5U4.png)

To add a new page of settings to the Mod Settings menu, create a new Widget Blueprint and parent it to WBP_ModSettingsBase. Override the GetSettingsHierarchy interface function, and create Map and Array literals to sketch the menu hierarchy. The S_SettingsTree struct allows each child item within the submenu to have 1 or many children of its own. Multiple settings pages can be added to the tree using this function, if needed.

3) Create a new Widget Blueprint parented to WBP_ModSettingsBase, and override GetSettingsHierarchy to define the position in the Settings menu where the settings page will be displayed.

<a href="https://i.imgur.com/henvduG.png" target="_blank" rel="noopener noreferrer">![settings hierarchy](https://i.imgur.com/uDbsBVf.png)</a>

The settings widget blueprint you created in Step 3 can be configured to save its settings to a file on the Client or Server using the Persistence Type option. Sessional doesn't save to a file, so settings changed only last until the game is closed. The Permissions Type option is used to determine who can access the settings page in the Main Menu. Using the Cameraman permission requires that the player have toggled admin cam on to see the settings. The Whitelist permission type checks the player's Steam ID against the list provided in the SteamIDWhitelist option in the class defaults. Default Filename should be set to something unique even if Sessional persistence is used, and should be similar to the name of the settings page. Default Namespace can be changed if desired, otherwise leave default. The Backup option can be set to a data table asset for restoring backups if needed. It's ok to leave this blank if you are defining settings controls manually, since the settings control defaults will be used in that case.

4) Configure class defaults for your Widget Blueprint as needed.

<a href="https://i.imgur.com/fxAb2mT.png" target="_blank" rel="noopener noreferrer">![settings class defaults](https://i.imgur.com/SOeunvE.png)</a>
