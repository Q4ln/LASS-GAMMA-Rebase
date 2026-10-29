# Ladies and Sister Stalkers - GAMMA Rebase

Version `d2026.10.28.1`

The Ladies and Sister Stalkers (LASS 2.1) female player character for GAMMA, as a
Female pack for GAMMA Character Selector. Choose Female on the New Game screen to
play with the LASS female bodies, first-person hands, voices, movement and
headgear sounds, health-HUD silhouette, video portraits and female-addressed
dialogue. Male characters stay as in GAMMA, and so do NPCs and mutants apart
from their step sounds and 31 NPC suit textures, because this build writes over
no other GAMMA or Anomaly file.

## What it does

- Registers the gender **Female** with GAMMA Character Selector. Female appears
  on the New Game screen next to Male and is preselected the first time; after
  that the New Game screen restores your last choices, gender included. Choose
  Male there to play GAMMA's own character.
- For a Female character only, the Selector applies the pack:
  - female third-person bodies for every GAMMA outfit, and a female body with no
    outfit (also used for the visible first-person legs);
  - female first-person hands for each outfit, including the KSG-23, TOZ-34 and
    bolt hand offsets and the bolt's own models, animations and sounds;
  - the female player voice in Russian and English through VAREFINED, with
    helmet muffling;
  - female footsteps, jumps, landings, crouch, stand and lean sounds;
  - female item-use, gas-mask breathing, mutant-looting, ledge-grab and
    artefact-perk sounds;
  - the six LASS gas-mask and helmet equip and unequip sounds;
  - the female Body Health System HUD atlas;
  - the animated female portraits for every faction, played as Ogg Theora
    videos;
  - female-addressed dialogue and task text (Russian and English);
  - NPC voice lines that the LASS team re-recorded, swapped or silenced so NPCs do
    not address a female player as a man.
- What changed from the old Rebase: when you play Male, NPCs look and sound like
  GAMMA again, apart from the step sounds and suit textures below. The LASS
  files that used to replace GAMMA's own files now live in the
  mod's own folders (`lass\female`, `lass\npc`) and are used only for Female.
- What it still changes for everyone: GAMMA's NPC and creature step sound bank
  (`sounds\material\human\step`, 66 files), which GAMMA's material pairs also
  use for some mutant steps and object impact sounds, and 31 NPC suit texture
  files. Those are loaded once for all characters, so they cannot follow the
  chosen gender.
- Apart from those files, a game that is not Female plays exactly as GAMMA: a
  Male character, a save with no gender, and a new game started from the
  console keep GAMMA's models, hands, player voice, sounds and text. The New
  Game screen always has a gender selected, so the console is the only way to
  start a new game without one.
- It removes nothing that LASS shipped. Whole-file text and config replacements
  became per-gender text and Selector rows.
- The animated portraits are 14 Ogg Theora videos that sit next to the LASS
  frame animations, which keep their old paths. Fifteen empty files,
  `textures\ui_a_portret_animated_female_*.ogm`, make the engine draw each
  portrait with its video shader. Do not delete them: without them the
  portraits show in yellow and olive tones on DX10 and DX11.

## Requirements

- S.T.A.L.K.E.R. Anomaly 1.5.3.
- GAMMA, modpack definition 920 (built and checked against it; played only
  briefly in game, see Known issues).
- **GAMMA Character Selector d2026.10.26.1 or newer.** This build has no standalone
  mode: without the Selector it does nothing.
- The Modded Exes build that GAMMA installs. The portraits are Ogg Theora
  videos, which the game engine plays as textures; they were seen playing on
  Modded Exes MT-TEST 2026.05.15 with DX11. There is no fallback to the frame
  animations: whenever a portrait's video is present, the engine plays it
  instead, on every renderer.
- Optional: the separate portrait add-on listed under Compatibility and
  conflicts.

## Installation

1. Exit Anomaly completely.
2. Remove the old overwriting Rebase and the original LASS mod, whatever their
   MO2 folder is called:
   - the original `Ladies and Sister Stalkers` mod (LASS 2.1);
   - every older build of this Rebase (the single archive from July 2026 and
     earlier). Older builds overwrite GAMMA's files and are sometimes installed
     under the folder name `Ladies and Sister Stalkers` too.

   Also remove the separate `LASS - Female Body Health Icon` mod; its atlas is
   part of this build. Remove the add-on
   `Ladies and Sister Stalkers - GAMMA Rebase - Headgear HUD Sounds` and the mod
   `LASS - OGM Animated Portraits` too, if you have them: their files are part
   of this build, and an old copy only duplicates them. The Selector recognises
   the files of the original mod and of the old Rebase. While any of them is
   installed, the New Game screen shows "Incompatible character files are
   installed", followed by "The old overwriting LASS GAMMA Rebase or original
   LASS files are installed..." and the name of the file it found. Every
   gender, Male included, is then Unavailable, and saves made with the Selector
   are refused with "This character cannot be loaded".
3. Install GAMMA Character Selector d2026.10.26.1 or newer.
4. Install this archive with MO2 and enable it.
5. MO2 priority: give it higher priority than every GAMMA mod, that is, place
   it lower in MO2's left pane than all of them (the end of the list is fine).
   Only the step sound bank and the 31 NPC suit textures overwrite files, and
   they take effect only if they win over GAMMA's copies, so it must sit below
   these GAMMA mods, which ship the same files:
   - the step sound bank: `G.A.M.M.A. Footsteps` and
     `3- Soundscape Overhaul - Solarint`;
   - the NPC suit textures: `29- Dux's Innemurable Characters Kit - DuxFortis`,
     `31- Fixed Vanilla Models and Textures - Blackgrowl`,
     `32- FVM Nosorogs models - Blackgrowl` and
     `386- PS6 Voin and Aztec NPCs Overhaul - Strogglet15`.

   Placed above any of them in the left pane, those LASS files lose without any
   message. Everything else overwrites nothing.
6. Start a new game. Female is preselected on the New Game screen the first
   time; after that the screen restores your last choices.

## Compatibility and conflicts

- Built for GAMMA Character Selector's external-pack interface: package `lass`,
  marker `configs\lass_gcs_female_pack_v1.ltx`, pack
  `configs\plugins\gcs\packs\50_lass_female.ltx`.
- Works with GAMMA's own scripts. VAREFINED, AGDD, FDDA, the Body Health System
  and GAMMA's footstep and jump scripts stay authoritative; the Rebase adapts to
  them instead of replacing them.
- Conflicts: the old overwriting Rebase, the original LASS mod, the separate
  LASS health-icon mod and the older separate headgear-sound and video-portrait
  mods (remove them; see Installation). Another mod that registers a gender
  with the ID `female` disables both copies in the Selector.
- Mods that change GAMMA's step sound bank or the NPC suit textures listed above
  decide the result by MO2 priority: the mod lower in MO2's left pane wins.
- Portrait add-on (a separate mod, optional):
  `LASS - Original Trio Animated Portraits` adds three animated portraits
  (blonde, black-haired, red-haired) to every Female faction, only for Female.
  Its own notes and README still name an older Rebase build, from July 2026, as
  its requirement and mention the retired separate video-portrait mod as
  optional; skip that mod, because this build already plays the portraits as
  videos. Install the Trio as its own MO2 mod next to this one.

## Options

No options of its own. The voice options (**MCM > VA Refined**), the movement
sound options (**MCM > Sounds > Movement**) and the Modded Exes
first-person-body option (**Options > Modded Exes > Gameplay > General >
First Person Body Legs (g_legs)**, or `g_legs 1` in the console) keep working
as in GAMMA.

## Adding or removing mid-save

- Adding: start a new game and choose Female.
- Saves made with the old Rebase and Selector rc15: Female saves keep their
  Female character and load once this build and GAMMA Character Selector
  d2026.10.26.1 or newer are installed.
  Male saves load too; the Selector drops their old requirement on the LASS
  package, so they no longer need any LASS mod.
- Saves made before GAMMA Character Selector was installed, for example with
  the old Rebase alone, have no gender. They load as a plain GAMMA character:
  GAMMA's default model and hands, player voice, sounds and text. They keep the
  portrait they were created with, so a female animated portrait chosen with
  the old Rebase stays. They cannot be turned into a Female character; start a
  new game for that.
- Removing: a Female save needs this mod to load; the Selector refuses it with
  "Missing gender: female" instead of loading a broken character. Male saves do
  not need this mod.

## Uninstall

Disable or remove the mod in MO2. Female is no longer offered on the New Game
screen; if your last New Game choice was Female, the screen shows it as
"Unavailable: female" and refuses to start until you choose Male. Female saves
cannot be loaded until the mod is installed again. No settings are left behind.

## Known issues

- In game this build has only been played briefly: one new Female game with
  the Character Selector, including loading one of its saves. Male games with
  this mod installed, saves from the old Rebase and long play have
  not been tested in game yet. Report crashes with the newest `xray_*.log`
  from Anomaly's `appdata\logs` folder.
- The portrait videos were seen playing in game, but their colours with the
  empty video-shader files have not been checked yet.
- One Russian line, Voronin's briefing `voronin_living_legend_3`, is not the
  LASS text. LASS edited the older vanilla briefing in
  `st_dialogs_lostzone_ll.xml`, but GAMMA replaces that briefing for every
  player from `zzzzz_clearsky_dolg_enemies_diaglos.xml`, a file that loads
  after the LASS one. A Female player sees GAMMA's briefing with its one
  masculine address made feminine ("будешь внимательна"). The old Rebase alone
  showed GAMMA's masculine line; Selector rc15 showed the LASS edit of the
  vanilla line.
  Apart from this line, a Female player sees every LASS text edit.
- With the Original Trio pack, its three portraits use the Selector's static
  pictures as thumbnails instead of a frame of the animation.
- A save made before the Character Selector was installed has no gender and stays
  a GAMMA character; with the old Rebase its character without an outfit showed
  the female body, and now it shows GAMMA's default model.
- GAMMA's optional 1st Person Visible Body mod (disabled by default) has HD leg
  models, behind its MCM option, that name many textures no GAMMA mod supplies.
  The old Rebase supplied six of them for every character; this build carries
  those six under `lass\female` and no longer applies them, so with that option
  those legs look as in GAMMA without this mod, for every gender.
- The NPC and creature step sound bank and the 31 NPC suit textures still
  change every character, Male included. GAMMA's material pairs also play those
  step sounds for some mutant steps and object impacts.

## Changelog

### d2026.10.28.1

- Female is offered on the Character Selector's New Game screen again.
- The game removes spaces from LTX values, so the two FDDA Redone medkit sounds
  now ship in `fdda_redone_stim_and_medkit_reanimation`, the folder the Female
  voice routes name.

### d2026.10.27.1

- The six LASS headgear sounds (gas mask and helmet equip and unequip) are part
  of this archive and always play for Female; the separate add-on
  `Ladies and Sister Stalkers - GAMMA Rebase - Headgear HUD Sounds` is retired
  (remove it).
- The animated portraits play as Ogg Theora videos: the 14 videos and 15
  video-shader files of `LASS - OGM Animated Portraits` are part of this
  archive, byte for byte, and that mod is retired (remove it).

### d2026.10.26.1

- Rebuilt as a Female pack for GAMMA Character Selector d2026.10.26.1 or newer;
  it requires the Selector.
- No longer overwrites GAMMA or Anomaly files, except the step sound bank and 31
  NPC suit textures. Male characters and NPCs look and sound like GAMMA again,
  apart from those files. This includes GAMMA's optional THAP Re-work and 1st
  Person Visible Body mods, which are disabled by default: when enabled, their
  gloves, sleeves and legs look exactly as in GAMMA, also where the HD legs name
  textures that only the old Rebase supplied.
- Female is offered on the New Game screen and preselected the first time. Female
  text, portraits, health atlas, sounds, bodies and hands apply only to Female.
- NPC voice lines changed by LASS apply only while playing Female.
- The female copies of 71 DesmanMetzger, FDDA and Dark Signal sounds that another
  GAMMA mod overrides are carried, so Female keeps the LASS versions.
- The ten first-person hand models the old Rebase changed for every outfit
  section now change only for Female.
- The female player voice, its companion-wheel lines and its voice settings
  apply only to Female; Male, saves with no gender and console new games keep
  GAMMA's player voice.
- Every player sound LASS changed follows the chosen gender, including gas-mask
  breathing, item use with and without FDDA, and mutant looting.
- Female-addressed text also reaches close captions, script-built dialogue
  lines, PDA achievements, item descriptions and tasks given during play.
- The six LASS headgear sounds no longer overwrite GAMMA's files.

### d2026.7.18.1

- Standalone rebase of LASS 2.1 on the GAMMA snapshot of July 2026, with the
  female Body Health System atlas merged in.

## Credits

- **Female content:** the LASS 2.1 team - Paint_Thinner, KILIMANAJARO,
  Alex_Marheaves, Blackbomb, MiK_ and Isthar: female bodies and outfits, female
  hands, player voice recordings, the female footstep, jump and lean banks, the
  gas-mask and helmet sounds, the animated portraits, the body texture sets and
  the NPC voice edits.
- **Movement scripts the adapter is based on:** oleh5230 (GAMMA's footstep and
  jump scripts, Extended MovementSFX) and CustomBeerFairy and ForserX (the jump
  sound ray casting).
- **Voice lines:** DesmanMetzger (Voiced Actor, Voiced Actor Refined, Injury Audio
  Extended).
- **Item-use sounds:** Feel_Fried (Food, Drugs and Drinks Animations, FDDA) and
  Dark Signal UI Audio.
- **Base meshes and textures:** GSC Game World (body models); Anomaly; THAP
  Rework by IENCE and Teivaz's Gunslinger Exo Animations Port (hand models and
  glove textures); Max_im16 (THAP Re-work glove and sleeve textures); the SWM
  team and Wang_Laoshi (1st Person Visible Body leg textures); DuxFortis (Dux's
  Innumerable Characters Kit textures);
  toxicfox777 (Better Bullet Casing bolt texture); the Gunslinger team (bolt
  holster sound); GAMMA Large Files.
- **Cigarette animations:** based on Asnen and Grok's Better Cigarettes
  Animations and lizzardman's FDDA Redone.
- **Female text edits based on:** G.A.M.M.A. Massive Text Overhaul (SageDaHerb,
  Dr.Pr1nkos), Dialogues Expanded (indyora), New Tasks (iTheon), Demonized,
  Darkasleif and vanilla Anomaly.
- **Copies of other mods' files that this build ships**, so the female hands keep
  the textures and animations they had with the old Rebase (pixels and geometry
  unchanged; only texture and animation references point at the female copies):
  - vanilla Anomaly (GSC Game World and the Anomaly team): the first-person hand
    model `wpn_hand_01` and its arm texture `act_arm_1`;
  - THAP Rework by IENCE: the `cod_ghosts_fed_gloves_cs`, `_merc` and `_mono`
    glove textures, three bump maps and 21 texture settings files;
  - Teivaz's Gunslinger Exo Animations Port: one bump map and one texture
    settings file;
  - Better Bullet Casing by toxicfox777: the bolt texture.
- **Female Body Health System atlas:** made for the "LASS - Female Body Health
  Icon" mod after GAMMA's Body Health System layout.
- **Video portraits:** Q4ln encoded the LASS team's animated portrait frames as
  Ogg Theora videos and made the video-shader files.
- **Framework:** G.A.M.M.A. by Grokitach and contributors; VAREFINED; GAMMA
  Character Selector.
- Texture families carried as LASS 2.1 shipped them: the hoc bolt, cp2077, Call
  of Duty, bf4, pla_swat, mili_flak and tigg sleeve, watch_tracer, kng
  sierra_head, gscfokya, handskilimaka and nails textures.
- Rebase, restructure and build: Q4ln.

## Licence

The Rebase's own code and build are by Q4ln under CC BY-NC-SA 4.0; see
`Ladies and Sister Stalkers - GAMMA Rebase - LICENSE.txt`. The LASS team's assets
and every other third-party asset remain under their authors' terms.
