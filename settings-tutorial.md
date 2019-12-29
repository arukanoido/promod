---
layout: default
title: Settings Tutorial
---

# Squad ProMod settings module tutorial

The settings component comes in 2 parts: the Config Parser, and the Mod Settings UI kit. The Mod Settings UI kit includes a component called BP_MainMenuModSettings which is added to the HUD and adds the Mods settings menu in the game Main Menu.

1) Add BP_MainMenuModSettings component to your HUD class override.

<a href="https://i.imgur.com/FOHe1jo.png" target="_blank">![main menu mod settings](https://i.imgur.com/L6DKtpA.png)</a>

For settings to be persisted to disk on the client or server, BP_SettingsPlayerState and BP_SettingsGameState overrides are provided which include the necessary RPCs for managing read and write. These overrides should be placed last in the reference chain. If you already have overrides for PlayerState and GameState classes, reparent BP_SettingsPlayerState to BP_YourPlayerState class (and the same for BP_SettingsGameState) or if not, reparent BP_SettingsPlayerState to Squad's default classes, called SQPlayerState and BP_GameStateSquad respectively.

2) Reparent BP_SettingsPlayerState and BP_SettingsGameState as the child of any existing PlayerState or GameState classes, and set them as overrides in your GameMode class.

[reference tree](https://i.imgur.com/DcbLwdG.png)
