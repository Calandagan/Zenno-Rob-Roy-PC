# Zenno Rob Roy · PC Edition

Zenno Rob Roy PC Edition plays complete Career runs of *Umamusume: Pretty Derby* on **Steam (Global)**, in the background: the bot clicks inside the game without moving your mouse or taking focus, so you can keep using your computer while it runs.

It is the PC counterpart of [Zenno Rob Roy](https://github.com/Calandagan/Zenno-Rob-Roy) (emulator edition). Both editions share the same license key.

> Download, extract and play: no emulator, no Python and nothing else to install. This repository hosts the documentation and the [Releases](https://github.com/Calandagan/Zenno-Rob-Roy-PC/releases).

## Main Features

- Complete Career automation from scenario selection through the final results.
- Background play: the bot never moves your mouse or brings the game to the front.
- Configurable training priorities, stat targets, failure limits and recovery behavior.
- **Biwa Hayahide** goal planning toward your stat targets, built on your own scoring rules.
- Support-card bond, rainbow training, hints valued by the skills they teach, energy, mood and stat-cap awareness.
- Infirmary visits for negative statuses.
- Scheduled races, eligible replacement races, race retries and debut-loss recovery.
- Event choices: your own overrides, Classic weights or the optional **Smart** mode with a risk tolerance.
- Required skills, priority groups, blacklists, discounts, prerequisites, automatic skill purchasing and an optional spend of leftover points.
- Your in-game support-card decks in your presets: pick one and send its hint skills to Required, Priority or Blacklist.
- **Independent Training** loops: wait for the game's clock, collect, buy skills, complete and start the next one.
- **Dailies:** Team Trials, Daily Sale, Daily Races and Daily Legend Races.
- Presets, scheduled tasks, Runs & Stats with detailed Run details, and detailed logs.
- A watchdog that recovers stuck screens: it unsticks, restarts the task and, as a last resort, restarts the game (limited per hour), with sound and Discord alerts.
- Optional Discord notifications for completed Careers, manual stops and errors.
- Built-in tools: Champions Meeting reference, CM Team Planner (from your own account), Race Simulator, HP Calculator and Career Lab.
- Dashboard in English, Spanish, Portuguese, French and Italian.

## Compared with the Emulator Edition

- **No emulator.** It runs on the Steam client: no MuMu, ADB, root or emulator settings.
- **Background play.** You keep the mouse and the keyboard while the bot plays.
- **One-button start.** START SESSION opens the game through Steam and starts everything.
- **New in the PC edition:** Independent Training, Career Lab, Smart events, the Infirmary, the new watchdog, the Happy Meek value model and the account-based CM Team Planner.

Your emulator presets show up read-only; **Copy to Rulership** makes your own editable copy.

## Supported Scenarios

| Scenario | Status | Dedicated automation |
| --- | --- | --- |
| URA Finale | Supported | URA training, race planning and Happy Meek duels decided by value |
| Unity Cup | Supported | Scenario bonuses, Team Showdowns and the final showdown |
| Trackblazer | Supported | Shop, inventory, item effects, race economy and Rival Races |
| Grand Live | Supported | Performance currency, lesson and song economy, Light Hello and concerts |

Each scenario keeps its own rules, so an item or rule from one scenario is never applied to another. If the game shows a different scenario than the task's, the bot stops instead of starting it.

## System Requirements

- Windows 10 or Windows 11, 64-bit.
- Microsoft Edge WebView2 Runtime. It comes with Windows 11 and updated Windows 10; if it is missing, the launcher tells you and offers Microsoft's download page.
- *Umamusume: Pretty Derby* installed from **Steam** (Global).
- A valid Zenno Rob Roy license key (the same key as the emulator edition).
- An active internet connection.
- An NVIDIA GPU is optional; see [GPU Pack](#gpu-pack-nvidia-optional).

The DMM version of the game is not supported yet.

## Installation

1. Open the [Releases](https://github.com/Calandagan/Zenno-Rob-Roy-PC/releases) section.
2. Download `ZennoRobRoyPc-<version>-win64.zip` and its `.sha256.txt` file.
3. [Verify the download](#verifying-a-download).
4. Extract the whole ZIP into a normal folder, for example `C:\Games\ZennoRobRoyPc`. Do not run it from inside the ZIP.
5. Close Umamusume if it is open.
6. Run `ZennoRobRoyPc.exe`.
   If Windows SmartScreen says "Windows protected your PC", choose **More info → Run anyway**. The build is not code-signed yet.
7. In **Access & updates**, paste your license key and press **Activate**.
8. Press **START SESSION**.
   - The first time, the launcher prepares the game folder. If Windows asks for permission, accept it.
   - Then it opens Umamusume through Steam, starts the bot and opens the dashboard in your browser.
9. In the dashboard, create or select a preset, review its settings and start the task.

Next times, just open the launcher and press **START SESSION**.

## Verifying a Download

Open PowerShell in the folder containing the ZIP and run:

```powershell
Get-FileHash .\ZennoRobRoyPc-<version>-win64.zip -Algorithm SHA256
```

Replace `<version>` with the downloaded version and compare the result with the accompanying `.sha256.txt` file. The values must match exactly. The same applies to the GPU pack.

## Updating

1. Stop the bot and close the launcher.
2. Download the new ZIP from [Releases](https://github.com/Calandagan/Zenno-Rob-Roy-PC/releases) and verify it.
3. Extract it over your current folder and replace the files.
4. Open the launcher and press **START SESSION** as usual.

Your settings, presets, logs and license are stored in your Windows profile, not in the launcher folder, so nothing of yours is lost.

## GPU Pack (NVIDIA, optional)

With an NVIDIA graphics card, the optional GPU pack makes the screens where the bot reads text faster. The bot works without it, and the pack does nothing on AMD or Intel graphics. It takes about 3.7 GB once extracted.

Most releases keep the same GPU pack, so the one you already have keeps working. Each release says which pack it uses:

| Launcher | GPU pack |
| --- | --- |
| 0.3.0 | 0.2.0 |

> The text file inside GPU pack 0.2.0 says it works only with launcher 0.2.0. That text is outdated: pack 0.2.0 is the right pack for 0.3.0.

**To install it**, close the launcher and extract the pack into the folder that contains `ZennoRobRoyPc.exe`. If Windows asks, replace the files. In **Game & bridge**, "Text reading (OCR)" shows the pack version.

**If a release needs a new pack**, the launcher says **Old GPU pack** and which one to get; until then the bot keeps working without it. To replace or remove the pack, delete the folder `Rulership\ChocoBourbon\ocr-gpu` and, to replace it, extract the new one.

If your card or its driver cannot run the pack, the bot goes back to the normal mode by itself. Nothing breaks; it is only slower. A current NVIDIA driver is recommended.

## Good to Know

- **The launcher never closes the game.** If it needs the game closed, it asks you first.
- **After a game update**, the launcher may warn that the new game version has not been checked yet. It keeps working if everything starts normally.
- **Game window.** The bot is tuned for a game window of 1308 × 736. START SESSION opens the game at that size, and while a session runs the launcher puts it back if it changes. It never moves the window or brings it to the front. To turn this off, use **Don't resize** in **Game & bridge**.
- **Hachimi is not needed.** If you use it for translations, it keeps working.
- **Remove mods** (Game & bridge) puts the game folder back the way it was.

## Known Limitations

- Steam (Global) only. The DMM version is not supported yet.
- Club dailies (shoe requests and donations) are skipped on Steam; do them by hand.
- The bot is tuned for a 1308 × 736 game window; full screen and other sizes are not supported.
- Independent Training uses agenda slots 1–3.
- The Steam overlay and some other mods can hang the game at startup.
- No built-in updater: new versions are ZIPs on the Releases page.
- The build is not code-signed, so SmartScreen warns the first time.
- A hung game is not force-closed by default: the bot pauses and alerts you.

## Recommended First Preset

Before starting a full unattended run, review:

- Career scenario.
- Target stats and training weights.
- Maximum accepted failure rate.
- Required and optional skills.
- Event-choice overrides.
- Scheduled races and adaptive race settings.
- Scenario-specific options.
- Automatic or manual final skill purchasing.

Run a short supervised test whenever you create a substantially different preset or install a major update.

## Troubleshooting

### Start does not finish or a check is red

Open the **Game & bridge** tab. Every check says what is wrong and, when it can, offers a button to fix it.

### The dashboard does not open

Use **Open dashboard** in the launcher.

### The GPU pack is not used

- Confirm the pack matches your release (see the [GPU Pack](#gpu-pack-nvidia-optional) table).
- Confirm you extracted it into the folder that contains `ZennoRobRoyPc.exe`, not into a new subfolder.
- Update the NVIDIA display driver.

### Reporting a problem

1. In **Game & bridge**, press **Copy diagnostics**.
2. Paste the text in our Discord, together with the newest files from `%LOCALAPPDATA%\Rulership\launcher\logs`.

## Community

For announcements, support and update information, join the [official Discord](https://discord.gg/QJcnuXDKxv).

## Disclaimer

Zenno Rob Roy is an independent community project. It is not affiliated with, endorsed by, or sponsored by Cygames, Inc., Valve Corporation, or any other rights holder associated with *Umamusume: Pretty Derby*.

Use automation at your own risk. Users are responsible for complying with the game's terms of service and for any consequences associated with their use of this software.
