# Scroll

<img width="640" height="400" alt="scrollscroll_125637_round_01" src="https://github.com/user-attachments/assets/caf185cc-aa3a-4873-9870-037025874656" />

<img width="640" height="400" alt="scrollscroll_125833_round_01" src="https://github.com/user-attachments/assets/9da66249-ff1d-4c76-aac5-d87d7af3a8fc" />

**Scroll** game mode: levels are stitched together and the screen scrolls non-stop.
Keep up, grab the chests and reach the goal portal; stragglers fall off screen and die.

A mod for **FortRise 5** (>= 5.3.3). The FortRise 4 version
(`tf-mod-fortrise-gamemode-speedrun`) is no longer maintained: fixes and new features
only land in this repository.

> The mode used to be called **Speed Run**. It is `Scroll` everywhere now - the mode on
> the versus screen, the mod in the options, the folder, the settings. The old name said
> "race to the finish", which is only one of the shapes it can take: with a square
> course and no goal portal it is a survival mode, and nothing is being run against the
> clock. What never changes is the screen scrolling on its own.

## Installation

1. Install FortRise 5 and start the game through `FortRise.exe`.
2. Copy `release/tf-mod-fortrise-gamemode-scroll` into `<TowerFall>/FortRise/Mods/`.

Settings are under **Options > Mods > Scroll**.
Log files live in `<TowerFall>/FortRise/Logs/`.

## Usage

<img width="759" height="677" alt="image" src="https://github.com/user-attachments/assets/8ca73e19-70d9-4217-99db-561a45cccc65" />

Pick the **Scroll** mode on the versus screen, then start the match.

> **Opening the popup**: on the versus screen, with the mode selected, press **Y** (the
> "arrows" button on the controller) on the mode button. A hint is shown under the
> button. The popup locks the menu while it is open (no going back, no starting the
> match); **A** or **B** closes it.


<img width="798" height="466" alt="image" src="https://github.com/user-attachments/assets/db916376-e09e-4cef-8368-e501c16c4b0d" />


<img width="775" height="668" alt="image" src="https://github.com/user-attachments/assets/163737d1-4255-4d1a-a91d-b24365a7621b" />


The popup tweaks the main settings without going through the options menu:

| Input | Effect |
|-------|--------|
| Up / Down | switch field |
| Left / Right | adjust the value |
| A or B | close |

It edits the module settings directly, so both screens always show the same values.
Some fields hide themselves when they no longer apply - the lap count only shows on a
square course with a goal portal, for instance.

Every change is written to disk immediately. FortRise only saves settings when leaving
the game's Options menu, so a value changed in the popup - or right before quitting -
used to be lost.

## Settings

Scrolling:

| Setting | Purpose |
|---------|---------|
| speed (tenths of px/frame) | scrolling speed |
| acceleration (+tenths px/frame) | gradual speed-up (0 = none) |
| acceleration every (s) | how often that speed-up applies |
| shape | horizontal strip or square loop course |
| camera | auto-scrolling camera or one that follows the players |

### Playing wide

There is no wide-screen option here any more. Widening the window is
[WiderSet](https://gamebanana.com/mods/608884)'s job: turn its mode on and Scroll is
played wide like everything else.

This mod used to resize the screen for its own rounds, which meant two mods owning the
same width - each recomputing the image centering over a value the other had just
changed, and the picture ending up off-centre. It reads the width now, it never sets it.

Course:

| Setting | Purpose |
|---------|---------|
| goal portal | goal portal, like the end of a co-op level |
| laps before goal (square) | laps before the goal opens (square course) |
| number of levels | how many levels are stitched together |
| leave players behind | stragglers fall off screen and die |
| offscreen death delay (s) | delay before that death |
| same spawn (race) | everyone starts from the same spot |
| intro zoom | wide shot then zoom in at the start |

Chests and rules:

| Setting | Purpose |
|---------|---------|
| treasure count | number of chests |
| treasure respawn (s) | chest respawn delay |
| treasure: ... | possible chest contents, one toggle per item |
| disable arrows | no shooting |
| disable head stomp | no killing by jumping on heads |

## Game mode icon

The mode has its own icon, at the size of the game's four (184x82) and in their style -
a silhouette in three shades of one colour, no black: a four-room tower with the screen
roaming inside it.

It used to be borrowed from WARLORD's, a horned head with nothing to do with the mode.
Two modes sharing one picture cannot be told apart in the list.

The file is `ModFile/Content/Atlas/gamemode.png`.

## Build / deployment

| Script | Purpose |
|--------|---------|
| `script/release.bat` | build, then assemble into `release/` |
| `script/deploy.bat` | copy `release/` into the TowerFall `Mods` folder |

Paths (game folder, module name) are set in `script/config.bat`.
