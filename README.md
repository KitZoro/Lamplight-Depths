# Lamplight Depths

![Lamplight Depths title artwork](assets/title.png)

**A modern furry dungeon expedition inspired by the compact, turn-based feel of DEC-era mainframe RPGs.**

Choose a species, choose a class, and descend through twenty dangerous levels in search of the Orb of Lamplight. Explore procedural dungeons, fight through a dedicated command-driven combat screen, recover treasure, and return safely to the guild before the depths claim it all.

Lamplight Depths is an original Linux game written in Python with Pygame Community Edition. Its code, setting, maps, names, music, sound effects, portraits, and tiles were created specifically for this project. Historical DND, Moria, and Angband files are not included.

## Features

- Six playable species: **Bunny, Fox, Ferret, Cat, Chicken, and Human**
- Four freely combinable classes: **Knight, Archer, Priest, and Mage**
- Twenty dungeon levels with steadily stronger monsters and a final Orb guardian
- Three campaigns with different danger and treasure levels
- Dedicated turn-based combat screen with direct letter commands
- Procedural rooms and corridors presented in a readable DEC-inspired split layout
- Species bonuses, class-specific skills, leveling, equipment supplies, and banking
- **Adventure mode** with defeat recovery and **Classic mode** with permanent death
- Autosaving, manual saving, atomic save writes, and older-save migration
- Keyboard and mouse support, resizable display, and F11 fullscreen
- Original two-minute ambient soundtrack and event sound effects

Every species can use every class, so combinations such as **Bunny Priest**, **Bunny Knight**, **Fox Archer**, and **Fox Knight** are fully supported and have their own portrait artwork.

## Campaigns

| Dungeon | Difficulty | Description |
| --- | --- | --- |
| Moonroot Warrens | Fair | A balanced first descent through old roots and buried halls. |
| Emberdeep Vault | Dangerous | Hot ruins populated by stronger monsters and richer treasure. |
| Glass Catacomb | Severe | A harsh expedition intended for experienced delvers. |

## Install on Linux

Download the latest ZIP from the GitHub **Releases** page, extract it, and open a terminal inside the `Lamplight-Depths` directory:

```bash
chmod +x INSTALL.sh run.sh
./INSTALL.sh
./run.sh
```

The installer creates a private Python environment and installs the exact supported Pygame version. On Ubuntu or Linux Mint, you may first need:

```bash
sudo apt install python3-venv
```

After installation, launch the game at any time with:

```bash
./run.sh
```

## Run from source

Requirements:

- Linux
- Python 3.10 or newer
- `python3-venv`
- Internet access during the first installation

Clone or download the repository, enter its directory, and run `./INSTALL.sh`. The game and its dependencies remain inside the project folder; no system-wide Python packages are changed.

## Controls

### Exploration

| Input | Action |
| --- | --- |
| WASD / Arrow keys | Move one turn |
| X | Move south, in the DEC tradition |
| E / Enter | Use stairs or interact |
| T | Light a torch for 120 turns |
| Space / Period | Wait one turn |
| F5 | Save manually |
| Esc / Q | Open the pause and save menu |
| F11 | Toggle fullscreen |
| M | Mute or unmute audio |

### Combat

| Input | Action |
| --- | --- |
| F | Fight |
| C | Use the current class skill |
| H | Drink a healing potion |
| E | Attempt to evade |
| S / Period | Stay and watch |
| 1–5 | Select an action directly |
| Arrow keys + Enter | Navigate and confirm an action |

Menus and combat choices can also be controlled with the mouse.

## How an expedition works

Gold found underground is only **carried gold**. It becomes safe **banked gold** when the adventurer reaches town alive. Banked gold can purchase healing potions and torches for later expeditions.

Returning to town also restores health and spirit. The guild remembers the deepest level reached, allowing the next expedition to continue from that depth.

- In **Adventure mode**, defeat costs all carried gold and returns the adventurer to town.
- In **Classic mode**, defeat permanently deletes that adventurer's save.

The game stores progress in `savegame.json` beside the executable. Copy that file somewhere safe if you want to back up an Adventure-mode character.

## Troubleshooting

### The game says Python's venv package is missing

On Ubuntu or Linux Mint, run:

```bash
sudo apt update
sudo apt install python3-venv
./INSTALL.sh
```

### The window opens but audio is unavailable

Lamplight Depths continues safely without audio if Linux cannot initialize an output device. Check the selected system output, close applications holding the device exclusively, and restart the game.

### Reset the local installation

Delete only the `.venv` directory inside the Lamplight Depths folder, then run `./INSTALL.sh` again. This does not delete `savegame.json`.

## Project structure

```text
Lamplight-Depths/
├── assets/          Original tiles, portraits, title art, music, and sounds
├── game.py          Game systems, interface, combat, saving, and rendering
├── INSTALL.sh       Linux dependency installer
├── run.sh           Game launcher
├── requirements.txt Python dependency versions
├── CHANGELOG.md     Release history
└── LICENSE.txt      MIT License
```

## Inspiration and originality

The interface and command-driven rhythm are inspired by the broad design language of Daniel Lawrence's DEC-era **DND** and other early dungeon expeditions. Lamplight Depths does not redistribute their program code or assets. It is a new game with original systems, campaigns, furry characters, graphics, audio, and writing.

## License

The original Lamplight Depths code is released under the [MIT License](LICENSE.txt). Copyright © 2026 Kit Zoro.

The included visual and audio assets were created for Lamplight Depths. See [LICENSE.txt](LICENSE.txt) for the package's current licensing notice.
