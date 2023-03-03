# KF2 v1090 Controlled Difficulty

This repo servers as an "how to" as well as file storage for demo and stat files. I don't expect anyone but me to use this repo, however if you'd like to play on older game version like us feel free to contact me about any issues.

# Overview

1. `Stats` directory contains all stat files from the games made by our group, they are parsed later into the [EU CD Spreadsheet](https://docs.google.com/spreadsheets/d/11ZmX_vSpSw9XvN_3jTNL2my6wz1EXyHJ9PR-2Bec5MQ/edit#gid=819535471)
2. `Demos` directory contains all demo files from the games made by our group, they are can be played in game by using `DemoPlay` command
3. `Server` directory contains `Controlled Difficulty` and `Custom Weapons` mods adjusted to v1090 version of the game.

# Demos

Demos are stored in the `Demos` directory. They are named as follows:
`<map name>_<game mode>_<difficulty>_<date>_<time>.demo`. To play a demo you have to:

1. Make `Demos` directory in your `Documents\My Games\KillingFloor2\KFGame` directory
2. Drag and drop a demo file into the `Demos` directory
3. Open the game and type `DemoPlay <demo name>` in the console

It is important to remember that by default demos are created with random numbers at the end like so `kf-lockdown-nightcore_zeds-56mm-2023_2_26#412.demo`. You have to remove the hashtag part to be able to play the demo like so `kf-lockdown-nightcore_zeds-56mm-2023_2_26.demo`.

# Client

To download the v1090 game client you have to download SteamDepotDownloader from [here] and install .NET Framework 6.0 or newer. After that you have to run the following command in the command line:
`dotnet <path_to_steam_depot_downloader>/DepotDownloader.dll -app 232090 -depot 232091 -manifest 2523132221870078133 -username <steam_username>`. After that you have to download the mods and place them just like in the server section. On top of that you have to make `steam_appid.txt` in `<Game_Dir>\Binaries\Win64` and put `232090` in it.

# Dedicated Server

To download game server for v1090 you have to download SteamDepotDownloader from [here] and install .NET Framework 6.0 or newer. After that you have to run the following command in the command line:
`dotnet <path_to_steam_depot_downloader>/DepotDownloader.dll -app 232130 -depot 232131 -manifest 5586479385902846317 -dir <directory_to_install>`
This will download the game server to the specified directory. After that you have to download the `Controlled Difficulty` and `Custom Weapons` and `SpawnVolumeEqualizer` mods from the `Server\Mods` (make sure to download TIM or other mods you wish to add) and place them in the `KFGame\BrewedPC` directory.

Launch the server like so `~/kf2server/Binaries/Win64/KFGameSteamServer.bin.x86_64 kf-containmentstation?GameLength=1?Difficulty=3?Game=Controlled_Difficulty.CD_Survival?mutator=TIM.TIMut,CustomWeapons.CustomWeaponsMutator,FriendlyHUD.FriendlyHUDMutator,SpawnVolumeEqualizer.SpawnVolumeEqualizer -Port=28960 -QueryPort=27015`
