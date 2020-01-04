---
layout: default
title: Settings Tutorial
---

# Squad ProMod Settings Module Tutorial

#### 1) Add BP_MainMenuModSettings component to your HUD class override.

The settings module comes in 2 parts: the Config Parser, and the Mod Settings UI kit. The Mod Settings UI kit includes a component called BP_MainMenuModSettings which is added to the HUD and adds the MODS settings menu in the game's Main Menu.

<a href="https://i.imgur.com/FOHe1jo.png" target="_blank" rel="noopener noreferrer">![main menu mod settings](https://i.imgur.com/L6DKtpA.png)</a>

#### 2) Add the BP_ConfigParser component to your GameState override class and your PlayerState override class.

For settings to be persisted to disk on the client or server, the BP_ConfigParser component includes the necessary RPCs for managing read and write. Add a Config Parser component to both your Game State override and your Player State override. If you don't already have child blueprints created for both classes, you will need to create them.

#### 3) Create a new Widget Blueprint parented to WBP_ModSettingsBase, and override GetSettingsHierarchy to define the position in the Settings menu where the settings page will be displayed.

To add a new page of settings to the Mod Settings menu, create a new Widget Blueprint and parent it to WBP_ModSettingsBase. Override the GetSettingsHierarchy interface function, and create Map and Array literals to sketch the menu hierarchy. The S_SettingsTree struct allows each child item within the submenu to have 1 or many children of its own. Multiple settings pages can be added to the tree using this function, if needed.

<a href="https://i.imgur.com/henvduG.png" target="_blank" rel="noopener noreferrer">![settings hierarchy](https://i.imgur.com/uDbsBVf.png)</a>

#### 4) Configure class defaults for your Widget Blueprint as needed.

The settings widget blueprint you created in Step 3 can be configured to save its settings to a file on the Client or Server using the Persistence Type option. Sessional doesn't save to a file, so settings changed only last until the game is closed. The Permissions Type option is used to determine who can access the settings page in the Main Menu. Using the Cameraman permission requires that the player have toggled admin cam on to see the settings. The Whitelist permission type checks the player's Steam ID against the list provided in the SteamIDWhitelist option in the class defaults. Default Filename should be set to something unique even if Sessional persistence is used, and should be similar to the name of the settings page. Default Namespace can be changed if desired, otherwise leave default. The Backup option can be set to a data table asset for restoring backups if needed. It's ok to leave this blank if you are defining settings controls manually, since the settings control defaults will be used in that case.

<a href="https://i.imgur.com/fxAb2mT.png" target="_blank" rel="noopener noreferrer">![settings class defaults](https://i.imgur.com/SOeunvE.png)</a>

#### 5) Add a Vertical Box (and make it a variable) and add controls to the Vertical Box from the provided control widgets. For each control, set a unique Key variable.

Continue building out the settings controls. It's required to add a Vertical Box, and make it a variable. 3 control types are provided, WBP_SettingsItem_Slider, WBP_SettingsItem_TickBox, and WBP_SettingsItem_TextBox for different needs, along with a WBP_SettingsHeader. For each control used, make sure to set the Key variable to the name of the settings key it is for.

<a href="https://i.imgur.com/ihwvlgx.png" target="_blank" rel="noopener noreferrer">![building the settings page](https://i.imgur.com/npMNZEN.png)</a>

#### 6) Add events to get user input from each control and use the variety of Set functions provided to set values in the correct format. The Set Simple functions allow a shorthand method that only requires passing the control widget to the function.

<a href="https://i.imgur.com/Lx7dDVt.png" target="_blank" rel="noopener noreferrer">![building the settings page](https://i.imgur.com/Xz7CRty.png)</a>

#### 7) Override the GetControlParent interface function to return the Vertical Box created in step 5.

<a href="https://i.imgur.com/Hh4eih7.png" target="_blank" rel="noopener noreferrer">![building the settings page](https://i.imgur.com/j4tF59l.png)</a>

#### 8) Use the set values in your code.

The standard way to access what values have been set is to get the Player State (if client side) or get the Game State (if serverside). Multiple helper functions are provided for retrieving settings values in different forms. You can go directly to the config parser component for values if you like. The BPFL function GetConfigParserComponent will return the Game State's config parser, a useful shortcut for serverside code. Settings values are automatically mirrored between client and server (if persistence type is serverside) so there should be no inconsistencies. There is an OnSettingsUpdated event on the PlayerState which triggers each time a setting is set, which can be used to update client code in realtime.

<a href="https://i.imgur.com/fNEvjSE.png" target="_blank" rel="noopener noreferrer">![using the settings values](https://i.imgur.com/klvQ4XB.png)</a>

---
