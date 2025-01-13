# X4 Chem Gate Builder

There is a tool to build gate connections for the game X4 Foundations. This tool has been created to help players to build connection between any sectors in the game. This tool creates a mod (extension) for the game, which can be installed and uninstalled easily.

## Features

Console and graphical user interface (GUI) versions are available. The GUI version is more user-friendly and has more features.

- Build gate connections between any sectors in the game.
- You can build any number of connections.
- Connection - it is a pair of the gates in two sectors.
- You can easily arrange the location of the gates in the sectors.
- In GUI version, after gate is initially defined, you can easily move it to another location.


## Requirements

    You have to have the extracted game files in your computer by the [X Catalog Tool](https://wiki.egosoft.com:1337/X4%20Foundations%20Wiki/Modding%20Support/X%20Catalog%20Tool/)

## Installation

Simple download the latest version of the tool from the [releases page]() and extract it to any folder.

You can start to build your connections right away.

## Usage

### Console version

Console version is a simple command line tool. You can run it from the command line and follow the instructions.

It has two command line arguments:
[list]
- `--extracted-path` - path to the extracted game files.
- `--log-level` - log level. Possible values: `DEBUG`, `INFO`, `WARNING`, `ERROR`, `CRITICAL`. Default value is `WARNING`.
[/list]

Example:
```bash
x4_chem_gate_builder_cli.exe --extracted-path "C:\X4\extracted" --log-level DEBUG
```

The interface is simple. From the beginning it will propose to you to select first sector ia a first connection:
```bash
? Select a sector: (Use arrow keys)
 » Antigone Memorial (Cluster_28_Sector001_macro) - Source: Vanilla
   Argon Prime (Cluster_14_Sector001_macro) - Source: Vanilla
   Asteroid Belt (Cluster_100_Sector001_macro) - Source: Extension: ego_dlc_terran
   Atiya's Misfortune I (Cluster_26_Sector001_macro) - Source: Vanilla
   Atiya's Misfortune III (Cluster_26_Sector002_macro) - Source: Vanilla
   Atreus' Clouds (Cluster_608_Sector001_macro) - Source: Extension: ego_dlc_boron
   Avarice I (Cluster_500_Sector001_macro) - Source: Extension: ego_dlc_pirates
```

After you select the first sector, it will propose to select the gate position in the sector:
```bash
? Select a sector: Argon Prime (Cluster_14_Sector001_macro) - Source: Vanilla
Existing Connections Zones in Cluster_14_Sector001_macro:
- connection_ClusterGate014To013                     : X:   50.00 km, Y:    0.50 km, Z: -110.00 km, to Second Contact II Flashpoint
- connection_ClusterGate014To007                     : X:  -90.63 km, Y:    0.00 km, Z:   95.91 km, to The Reach
- connection_ClusterGate014To706                     : X:  -94.98 km, Y:    0.00 km, Z:   21.30 km, to Hatikvah's Faith
- connection_ClusterGate014To029                     : X:   50.00 km, Y:    0.50 km, Z:  120.00 km, to Hatikvah's Choice I
Define coordinates for the gate in Argon Prime:
? Enter coordinates in km (X, Y, Z):
```
Additionally provide information about the existing gates in the sector.

After you select entered coordinates, it will propose to define the rotation of the gate:
```bash
? Enter coordinates in km (X, Y, Z): 50,50,50
Define rotation for the gate in Argon Prime:
? Enter rotation angles (roll, pitch, yaw in degrees):
```

After the the same steps will be repeated for the second sector.

When both sectors are selected and a gate is defined in each sector, the tool will ask to enter more connections.
```bash
? Select a sector: Asteroid Belt (Cluster_100_Sector001_macro) - Source: Extension: ego_dlc_terran
Existing Connections Zones in Cluster_100_Sector001_macro:
- connection_ClusterGate100To101                     : X:  -11.52 km, Y:    0.00 km, Z:  136.36 km, to Mars
- connection_ClusterGate100To048                     : X:  114.36 km, Y:    0.00 km, Z:  -61.52 km, to Getsu Fune
- connection_ClusterGate100To107                     : X:   41.41 km, Y:    0.00 km, Z: -130.61 km, to Jupiter
Define coordinates for the gate in Asteroid Belt:
? Enter coordinates in km (X, Y, Z): 50,50,50
Define rotation for the gate in Asteroid Belt:
? Enter rotation angles (roll, pitch, yaw in degrees): 0,0,0
? Will you add one more Gate connection? (y/N)
```

Then you will be asked to generate the mod (extension) for the game:
```bash
? Will you add one more Gate connection? No
? Should be extension files be generated? (Y/n)
```

If you select `Y`, the tool will generate the extension files in the `output` folder.

If it not empty, the tool will ask you to overwrite the existing files:
```bash
? Will you add one more Gate connection? No
? Output directory is not empty. Do you want to clean it? (y/N)
```

and then will generate the extension files.

```bash
? Output directory is not empty. Do you want to clean it? Yes
Script execution completed.
```

As a result, the extension files will be generated in the `output` folder. It will be a folder with name `chem_gate_keeper`.

Simply copy this folder to the `extensions` folder of the game and enable it in the game settings.

### GUI version
