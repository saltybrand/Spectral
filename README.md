# Spectral

Spectral is a Gorilla Tag mod menu for PC and VR, built in C# as a BepInEx plugin. It includes an in-game VR menu and a desktop interface for browsing and controlling modules.

Created by **Cha554, Meep670, and Nova**.

## Features

- Modules organized into categories including Movement, Player, Visuals, Fun, Room, and Sound Board.
- Desktop panels with search, tooltips, and an enabled-only filter.
- Customizable themes, layouts, button sounds, and saved preferences.
- Recently used modules and in-game notifications.


## How to get Spectral

Download the latest DLL in this Repo.

## Installation

You need the Windows PC version of Gorilla Tag and a compatible BepInEx installation. This project references BepInEx 5 assemblies and the Steam game's managed assemblies; it is not a standalone Quest APK.

1. Close Gorilla Tag.
2. Find your game folder through Steam: right-click **Gorilla Tag > Manage > Browse local files**.
3. If BepInEx is not installed, follow the [BepInEx installation guide](https://docs.bepinex.dev/articles/user_guide/installation/index.html) using a build compatible with your game. Launch the game once to generate its configuration and log, then close it.
4. Download `Spectral.Menu.dll` using this repo.
5. Place the DLL in the game's `BepInEx\plugins` folder. Remove any older Spectral DLL first so only one copy loads.
6. Launch Gorilla Tag.

Your installation should look like this:

```text
Gorilla Tag/
  BepInEx/
    plugins/
      Spectral.Menu.dll
```

## Controls

| Action | Default control |
| --- | --- |
| Open the VR menu | Hold the left controller's secondary button (Y on Touch controllers) |
| Open the VR menu with right-handed mode enabled | Hold the right controller's secondary button (B on Touch controllers) |
| Open the menu using a keyboard | Hold Q |
| Show or hide the desktop interface | Press F6 |

Use the desktop interface to search for modules, toggle them, and view their tooltips. Menu settings can change the default behavior.

## Settings and online services

Saved menu preferences live under:

```text
Gorilla Tag\Spectral Menu\Spectral_Preferences\
```

Spectral also uses a BepInEx configuration file:

```text
BepInEx\config\org.menu.spectral.mainmenu.cfg
```

The API client retrieves remote configuration and sends heartbeats containing a generated session ID, menu version, and module-use names. Its base URL is configurable through `[API]` > `BaseUrl` in that file. Update checks and downloads use GitHub.

## Troubleshooting

- **Menu does not appear:** press F6 for the desktop interface, or hold the default VR menu button. Confirm that the DLL is inside the correct game's `BepInEx\plugins` folder.
- **Plugin does not load:** inspect `BepInEx\LogOutput.log` for Spectral errors or missing dependencies. If no log is generated, check the BepInEx installation first.
- **Duplicate menus or unexpected behavior:** close the game and remove duplicate Spectral DLLs before restarting.
- **A module is missing or unavailable:** check access requirements and the online configuration status; some modules are restricted or remotely disabled.
- **A game update breaks loading or modules:** check for a compatible Spectral release. Source builds may need updated game references or code changes.
