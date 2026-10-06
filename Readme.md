# AxePower ⚡

**Power management and gaming optimizer for Windows laptops**

<div align="center">

![Platform](https://img.shields.io/badge/Platform-Windows%2010%2F11-blue)
![Framework](https://img.shields.io/badge/Framework-WPF%20%7C%20.NET%208-512BD4)
![License](https://img.shields.io/badge/License-MIT-green)
![Version](https://img.shields.io/badge/Version-2.1.0-blueviolet)

[Website](https://axepower.vercel.app/) • [Discord](https://discord.gg/WfD4wZFJ8d) • [Releases](https://github.com/mrAbhimanyuVishwakarma/AxePower_Download/releases) • [Help Center](https://axepower.vercel.app/help.html) • [Issues](https://github.com/mrAbhimanyuVishwakarma/AxePower_Download/issues)

</div>

AxePower is a set-and-forget tool for Windows laptops. It switches your power settings and display refresh rate depending on whether the charger is plugged in, so you get longer battery life when you're unplugged and full performance when you're not.

Over time it has also picked up a bunch of things I kept wanting on my own machine: a game launcher and Game Mode, system maintenance tools, a software installer hub, phone integration, a music player and screen sharing.

## Screenshots

<img width="1024" height="679" alt="dashboard_laptop" src="https://github.com/user-attachments/assets/c61c8ce8-658c-463c-a8ba-0b0784530b3e" />
<img width="2752" height="1536" alt="website_home_image" src="https://github.com/user-attachments/assets/a368bc5c-2c2a-4308-b304-edd10312996d" />

## Features

### Power modes

| Mode | What it's for |
| --- | --- |
| 🔋 **Eco** | Saves battery when you're away from the charger. |
| ⚖️ **Smart** | Middle ground for everyday stuff like browsing and video. |
| 🚀 **Beast** | Maximum power and sustained clocks for gaming or heavy work while plugged in. |
| 🎮 **Game** | Detects running games on any drive, suspends background bloat, locks the display to its maximum refresh rate, and offers controller navigation (Gopher360). |

With **Auto Switch** turned on, AxePower changes modes for you. By default it uses:

- **Plugged in:** Smart Mode
- **On battery:** Eco Mode
- **Low battery (< 30%):** Eco Mode

You can change these defaults in Settings.

### Gaming

- **Game library scanner** for Steam, Epic Games Launcher, Xbox / Microsoft Store (Game Pass), Ubisoft Connect, EA App and GOG Galaxy.
- Poster and box art from **SteamGridDB**, cached locally, with fallback graphics when nothing is found.
- **Controller navigation** for Xbox (360 / One / Series X|S) and PlayStation (DualShock 4 / DualSense) controllers, with an in-app guide to the button mappings. Toggle it with `Back + Start`.
- Quick-launch for OEM tools: Lenovo Legion Toolkit, Lenovo Vantage, ASUS Armoury Crate and MSI Center.

### Monitoring

- **CPU and GPU temperatures** from your machine's actual sensors. This still works on Windows 11 with **Memory Integrity** turned on, where MSR-only tools report nothing (see [Temperature sensors](#temperature-sensors)).
- Live 2x2 grid for CPU load and clock, GPU utilization and temperature, RAM usage, and network send/receive speeds.
- 24-hour battery history graph.

### Maintenance

- **System Care** – recommended tweaks, SFC/DISM repairs, junk cleanup, DNS tools, restore points and live terminal output, all in one place.
- **Windows Update controls** – apply a security-updates-only policy, block forced restarts while someone is signed in, reset the Windows Update cache and services, and create a restore point before making changes.
- **Uninstaller** – separate Win32 and Windows Apps tables with sortable columns, batch selection, broken-entry filtering and leftover scanning (with registry backups before cleanup).
- **Debloat** – runs Win11Debloat elevated.

### Utilities

- **Terminal** – a real CMD / PowerShell session inside the app. Every command AxePower runs (installs, upgrades, SFC/DISM, DNS benchmark) shows its output here, and there's a Stop button to cancel it.
- **Tools**, **Timer** and **If-Then Routines**.

### Software Hub

- One-click install / open / uninstall for game stores, hardware monitoring tools, drivers, runtimes and common apps.
- **Ninite** support: run the bundled multi-installer or open the Ninite builder for a custom package.
- Batch upgrades through WinGet (`winget upgrade --all`) or individual package upgrades.

### Media & sharing

- 🎵 **Music player** – local audio library, YouTube streaming, Spotify controls, a mini player in the dashboard header, and it follows your default Windows output device without needing a restart.
- 🖥️ **Share Screen** – stream your desktop or a game to friends through a link. Viewers just open it in a browser; nothing to install on their end.

<!-- TODO: Clarify whether Share Screen only works on the local network ("local web link") or can be reached by friends over the internet. -->

### Phone Control

- **LAN Drop** – offline Wi-Fi file sharing and clipboard notes between PC and phone via QR code.
- **scrcpy** – low-latency Android screen mirroring with stay-awake / screen-off toggles, resolution and FPS presets, and one-click APK sideloading.
- **spacedesk** – use a phone or tablet as a wireless second display.
- **Microsoft Phone Link** launcher.

### Accounts

Optional accounts and profiles, plus friends and invitations.

### Privacy

No telemetry, no analytics and no remote data collection.

<!-- TODO: The privacy statement above dates from v1.3.0. Since then, optional accounts, friends/invitations, YouTube/Spotify, SteamGridDB artwork and the GitHub update checker were added. Please confirm the statement is still accurate, or explain what (if anything) leaves the machine when those features are used. -->

## Requirements

- Windows 10 or Windows 11 (x64)
- .NET 8 Desktop Runtime – the installer sets this up for you

## Installation

1. Go to the [Releases](https://github.com/mrAbhimanyuVishwakarma/AxePower_Download/releases) page or the [AxePower website](https://axepower.vercel.app/).
2. Download **`AxePower-v2.1.0-Setup.exe`**.
3. Run the installer and go through the setup wizard.
4. AxePower starts automatically and sits in the system tray.

If an older version is installed, the installer closes any running instance and removes the old version before installing the new one.

## Usage

- AxePower lives in the **system tray**. The `✕` button in the title bar hides the window to the tray instead of quitting, so mode switching keeps working in the background.
- Right-click the tray icon to switch modes (Eco, Smart, Beast, Game) or jump to Battery Hub, Phone Control, Second Monitor, System Doctor, System Utilities, Update PC, Settings, or Exit.
- On the dashboard, picking Eco, Smart or Beast previews it; the mode is only applied when you click **Apply**.
- Dashboard tiles link to specific pages. For example, the Gaming Runtimes tile opens the Software Hub on the *Apps* tab with *Gaming* already selected.
- The `? Help` button in the title bar opens guides for each tool. Full docs live in the [Help Center](https://axepower.vercel.app/help.html).

The sidebar is organized like this:

- **Maintenance:** Windows Update, System Care, Uninstaller, Debloat
- **Utilities:** Terminal, Tools

## Configuration

Everything is in **Settings**:

| Setting | Notes |
| --- | --- |
| **Default modes** | Pick which mode (Eco, Smart, Beast or Game) is used when plugged in and on battery. |
| **Remember last selected mode** | Under *Startup*. Restores your last manually chosen mode when the app restarts. |
| **Run as administrator** | On by default. See below. |
| **Updates** | Toggle automatic update checks and background downloads. |
| **Notifications & Alerts** | Desktop banners, notices for automatic mode changes, and the low-battery chime. |
| **Theme** | Light, Dark, System or Glass. |

### Running as administrator

AxePower ships with an `asInvoker` manifest and elevates itself by relaunching, which is why you can actually turn the admin setting **off** (most tools don't let you).

- When it's on, the logon task is registered at `HighestAvailable`, so AxePower starts elevated at boot without a UAC prompt.
- If you're not elevated, a **Relaunch with Admin** button appears in the title bar.
- If you decline the UAC prompt, the app just keeps running as a standard user.
- The built-in Terminal runs with the same privileges as the app.

### Glass theme

Glass uses the Windows 11 Mica and Acrylic backdrops, and falls back to Acrylic blur-behind on Windows 10 and early Windows 11 builds. It replaced the old *Transparent* theme. Settings files that still say `Transparent` are migrated to `Glass` automatically.

### Updates

AxePower checks GitHub Releases for new versions. With background downloads enabled, the installer is saved to `%TEMP%\AxePower_Update\` and a banner offers **Restart & Install**.

## Temperature sensors

AxePower tries three sources, in order of reliability:

1. **Lenovo ACPI-WMI firmware** (`LENOVO_GAMEZONE_DATA`) – no kernel driver needed. It's the same interface Lenovo Vantage and Legion Toolkit use.
2. **MSI Afterburner shared memory** – no elevation needed, and the numbers match what Afterburner shows.
3. **LibreHardwareMonitor** – the usual MSR route through its own kernel driver.

Why bother: on current Windows 11, the MSR driver (WinRing0) is on Microsoft's vulnerable-driver blocklist. With Memory Integrity enabled, which is the default on new machines, tools that only use MSR quietly show nothing. AxePower falls through to whichever route still works.

If a reading comes from the ACPI chassis zone rather than the CPU die, the UI says so instead of showing an ambient temperature as your CPU temperature.

## Tech stack

- WPF on .NET 8
- LibreHardwareMonitor for sensor readings
- WinGet (Windows Package Manager) and USOClient for updates
- Windows DWM backdrops (Mica / Acrylic) for the Glass theme

## Credits

AxePower integrates or launches these projects:

- [scrcpy](https://github.com/Genymobile/scrcpy) by Genymobile
- LAN Drop by yadavnikhil03
- spacedesk by datronicsoft
- Win11Debloat by Raphire
- Gopher360
- MSI Afterburner by MSI / Guru3D
- LibreHardwareMonitor
- SteamGridDB
- Ninite

## Changelog

### v2.1.0 (current)

- **System Care:** Optimizer and Doctor are merged into one page with a collapsible category sidebar, recommended tweaks, guarded repair actions, junk cleanup, DNS tools, restore points and live terminal output.
- **Windows Update controls now work:** apply the recommended security-updates-only policy, block forced restarts while a user is signed in, reset the Windows Update cache and services, and create a restore point first.
- **Uninstaller is now table-based:** separate Win32 and Windows Apps views use the full page width and show each app's type. Columns are sortable (including A–Z / Z–A), with batch selection, broken-entry filtering and Select All for leftovers.
- **Software Hub layout:** categories moved to a collapsible left sidebar. Install and app actions stay on the right when there's room and move below the details when the window is narrow.
- **Notifications & Alerts:** desktop banners, automatic mode-change notices and the low-battery chime now respect saved settings and react to live events.
- **Mode selection fix:** only the applied mode shows as active. Choosing Eco, Smart or Beast previews its glow until you click Apply. Game Mode no longer makes Smart look active.
- **Navigation cleanup:** Maintenance now holds Windows Update, System Care, Uninstaller and Debloat; Utilities holds Terminal and Tools.
- **Also included from 2.0.x:** optional accounts and profiles, friends and invitations, more trusted tools, Timer, and If-Then Routines.
- Installer: **`AxePower-v2.1.0-Setup.exe`** (Windows 10/11 x64).

<details>
<summary><strong>v1.9.0</strong></summary>

- **Music player:**
  - In-app playback with a queue, track progress, volume control and background playback.
  - Stream audio from YouTube and control Spotify from inside AxePower.
  - Mini player in the dashboard header.
  - Follows changes to the default Windows output device without a restart.
- **Share Screen / GameStream:**
  - Stream your desktop or game session to friends through a local web link.
  - Viewers connect from any modern browser with low latency and synced audio; no client download needed.
  - Stability fixes for CamStudio and spacedesk virtual display resets.
- **Uninstaller Pro rework:**
  - New leftover scanner with confidence scoring, deeper registry and filesystem checks, and backup manifests before cleaning.
  - **Broken Entry Executor** for removing corrupted and orphaned uninstall entries from the registry.
  - Better detection for Win32 setups, MSI installers, Squirrel apps and AppX/MSIX packages.
- **Battery view:**
  - Cleaner battery history card with responsive sparklines.
  - Fixed binding errors and repeated settings writes during dashboard load, so it renders faster.
- **UX:**
  - Sidebar groups remember whether they were expanded or collapsed.
  - Installer: **`AxePower-v1.9.0-Setup.exe`**, which installs the .NET 8 Desktop Runtime and updates existing installs.

</details>

<details>
<summary><strong>v1.8.0</strong></summary>

- **Built-in Terminal (CMD & PowerShell):**
  - New **Terminal** page under *Maintenance* with a persistent interactive shell. Switch between PowerShell and Command Prompt and run commands.
  - Software Hub installs/upgrades and System Doctor diagnostics (SFC / DISM / DNS benchmark) now stream their output here instead of hiding behind a spinner.
  - A **Stop** button cancels whatever is running, including long diagnostics started from other pages.
  - The shell runs with the same privileges as AxePower.
- **Run as administrator:**
  - New **Run as administrator** toggle in Settings (on by default) and a **Relaunch with Admin** button in the title bar that hides once you're elevated.
  - Keeps an `asInvoker` manifest and elevates by relaunching, so the setting can be turned off.
  - Logon task registered at `HighestAvailable`, so AxePower starts elevated at boot with no UAC prompt.
  - Declining the UAC prompt no longer causes a loop; the app continues as a standard user.
- **CPU & GPU temperatures that work with Memory Integrity:**
  - New three-tier sensor stack: Lenovo ACPI-WMI (`LENOVO_GAMEZONE_DATA`), MSI Afterburner shared memory, then LibreHardwareMonitor. See [Temperature sensors](#temperature-sensors).
  - The UI labels readings that come from the ACPI chassis zone instead of the CPU die.
- **One-click restore point:**
  - Create a restore point from the Software Hub. AxePower enables System Restore on the system drive and removes the once-per-24-hours limit first, so the restore point actually gets created instead of being skipped.
- **Glass theme (Mica & Acrylic):**
  - Replaces the old *Transparent* theme, using the Windows 11 DWM backdrops with an Acrylic blur-behind fallback for Windows 10 and early Windows 11.
  - Settings files with `Transparent` are migrated to `Glass` automatically.
  - Light, Dark and System themes were tweaked too.
- **Dashboard quick actions:**
  - Tiles open the exact destination, e.g. Gaming Runtimes opens the Software Hub on *Apps* with *Gaming* selected.
  - Software Hub category chips now filter correctly.
- **Portability fixes:**
  - Removed paths from my dev machine that had ended up in the release build. The Ninite launcher is now found next to the installed executable.
  - NVIDIA / AMD control panel launchers are resolved with Windows folder constants instead of a hardcoded `C:\Program Files`, so they work when Windows isn't on C:.
  - Installer: **`AxePower-v1.8.0-Setup.exe`**, still installs the .NET 8 Desktop Runtime and removes older versions.

</details>

<details>
<summary><strong>v1.7.0</strong></summary>

- **Game Mode redesign and game library scanner:**
  - Detects installed games from Steam, Epic Games Launcher, Xbox / Microsoft Store (Game Pass), Ubisoft Connect, EA App and GOG Galaxy.
  - Poster and box art from SteamGridDB, cached locally, with fallback graphics.
  - Responsive grid of game cards with hover scaling, one-click launch and a shortcut to open the game folder.
- **Controller navigation:**
  - Gamepad navigation for Xbox (360 / One / Series X|S) and PlayStation (DualShock 4 / DualSense) controllers.
  - In-app visual guide showing the button mappings for mouse movement, clicking, scrolling and system controls.
- **OEM tool integration:**
  - Quick launch for Lenovo Legion Toolkit, Lenovo Vantage, ASUS Armoury Crate and MSI Center.
- **Other:**
  - Better background service suspension during games, and new tests for mode automation.

</details>

<details>
<summary><strong>v1.6.0</strong></summary>

- **Live 2x2 performance grid** (replaces the old sidebar widgets):
  - **CPU:** load % and clock speed (GHz).
  - **GPU:** Windows WDDM 3D engine utilization % and temperature for discrete GPUs (e.g. RTX 4060).
  - **RAM:** used/total GB and %.
  - **Internet:** Wi-Fi and Ethernet send/receive speeds.
  - Sparklines drawn with StreamGeometry, starting from a zero baseline, with filled areas.
- **24-hour battery history:** full-width card with a rolling 24-hour graph, time markers (`24h ago`, `12h ago`, `Now`) and a percentage badge.
- **Steam-style tray menu:**
  - Dark slate design (`#171A21`) with full-width dividers.
  - Four sections:
    - **Power Modes:** Eco, Smart, Beast, Game.
    - **Navigation & Monitoring:** Open AxePower, Battery Hub, Phone Control, Second Monitor.
    - **Maintenance & Updaters:** System Doctor, System Utilities, Update PC.
    - **System:** Settings, Exit AxePower.
- **Update banner and patch notes:**
  - A cyan/blue banner at the bottom appears when checking for updates or when an update is ready.
  - Steam-style patch notes dialog with a scrollable list of posts, `▲` / `▼` scroll buttons, and reaction buttons (`👍 Rate Up`, `👎`, `💬 Discuss`, `🔗 Share`).
- **Background auto-updater:**
  - Checks automatically and downloads installers in the background to `%TEMP%\AxePower_Update\`.
  - **Restart & Install** button in the banner launches the new installer and restarts AxePower.
  - Toggles for automatic checks and background downloads in *Settings → Updates*.
- **spacedesk and Microsoft Phone Link:**
  - One-click install of the spacedesk virtual display driver (`Datronicsoft.SpacedeskDriver.Server`) and a console launcher.
  - QR codes for the Google Play (Android), App Store (iOS) and HTML5 web viewer apps.
  - Phone Link launcher and Link to Windows pairing dialogs.
- **Audio and creative apps in the Software Hub:**
  - Dolby Access (Dolby Atmos), SteelSeries GG Sonar, Peace Equalizer APO, DaVinci Resolve, OBS Studio and Microsoft PowerToys.
  - Batch updates via PowerShell (`winget upgrade --all`) or per-package upgrades.
- **Window controls:**
  - New `? Help` button in the title bar, left of Minimize.
  - `✕` now hides the window to the system tray (`Hide()`) while background monitoring keeps running.
  - Settings and About pages tidied up, with the update checker aligned left.

</details>

<details>
<summary><strong>v1.5.0</strong></summary>

- **Ninite** added to Update PC and the Software Hub:
  - **Install** runs the bundled multi-installer with no extra clicks.
  - **Custom** opens the [Ninite](https://ninite.com/) builder to create your own package.
- **Help modal:** tool tabs now scroll horizontally so every tool (including Controller Navigation) is reachable.
- **Help Center website:** launched the [AxePower Help Center](https://axepower.vercel.app/help.html) with controller mappings, setup guides and search. The "Readme" button is now "Learn More" and links to the matching docs page.
- **Live battery info:** real-time battery metrics and charging status.
- **Firmware & BIOS checks** in Update PC.
- **Themes:** theme resources are fully dynamic, so switching between light and dark is instant everywhere.

</details>

<details>
<summary><strong>v1.4.0</strong></summary>

- **Sidebar reorganization:**
  - Settings and About pinned to the bottom of the sidebar.
  - Navigation grouped into **CONTROL**, **CONNECTION** (Phone Control), collapsible **MAINTENANCE** (Optimizer, Doctor) and collapsible **UTILITIES** (MSI Afterburner, Uninstaller Pro, Update PC, Debloat).
- **Controller navigation (Gopher360) in Game Mode:** use a gamepad / Xbox controller as a mouse and keyboard, with a mapping reference and a `Back + Start` toggle.
- **New default power rules:**
  - Plugged in: Smart Mode.
  - On battery: Eco Mode.
  - Low battery (< 30%): Eco Mode.
  - Improved manual mode selection.
- **Dashboard:** Eco, Smart and Beast cards are now the same size.
- **Stability:** discovery no longer blocks on timeouts, and dependencies were updated.

</details>

<details>
<summary><strong>v1.3.0</strong></summary>

- **Phone Control:**
  - **spacedesk virtual display:** one-click launcher and auto-installer to use phones and tablets as wireless second displays *(credit: datronicsoft)*.
  - **LAN Drop:** offline file transfer and clipboard note sync between PC and phone via QR code *(credit: yadavnikhil03)*.
  - **scrcpy:** low-latency Android mirroring, stay-awake / screen-off toggles, resolution and FPS presets, and one-click APK sideloading *(credit: Genymobile)*.
- **Software Hub:**
  - Steam, Epic Games Launcher, Rockstar Games Launcher, Ubisoft Connect, Battle.net, GOG Galaxy, EA App, DaVinci Resolve (Free), MSI Afterburner, CPU-Z, GPU-Z, HWiNFO, CrystalDiskInfo, OBS Studio, Discord, VLC, 7-Zip, Notepad++ and runtimes.
  - Two buttons per app: **Open** / **Uninstall** if installed, **Install** if not.
  - Three-stage install process that doesn't block on stdin and falls back to the official download page if needed.
- **No hardcoded paths:** paths are resolved dynamically, so it works on any drive (C:, D:, E:, …), any user profile and any system locale.
- **Smart Mode as default:** out of the box, Smart Mode is used for both AC and battery, with Eco, Smart, Beast and Game selectable in Settings. *(Changed in v1.4.0.)*
- **Remember last selected mode:** new toggle in *Settings → Startup*.
- **In-app tool guides:** step-by-step help for every sidebar tool, with shortcuts and Readme links.
- **Uninstaller Pro:** uninstalls Win32, MSI, AppX and WinGet apps, scans for leftovers and backs up the registry automatically.
- **Battery indicator:** larger live battery indicator in the header that shows AC Power / On Battery.
- **Website:** launched the [AxePower website](https://axepower.vercel.app/) with direct downloads from GitHub Releases.
- **Auto-updater:** checks GitHub Releases, downloads the installer with a progress bar and updates the app.
- **Win11Debloat:** one-click elevated run of the debloat and telemetry removal scripts *(credit: Raphire)*.
- **MSI Afterburner companion:** quick launch and focus for GPU tuning, fan curves and on-screen stats *(credit: MSI / Guru3D)*.
- **Update PC:** elevated one-click driver and Windows updates through Windows Package Manager / USOClient.
- **System tray:** dark tray menu with mode switching, plus a minimize-to-tray button in the title bar.
- **Clean upgrades:** the installer closes running instances and removes older versions before updating.
- **Privacy:** no telemetry, no analytics and no remote data collection.

</details>

## Support

- **Bug reports and questions:** [GitHub Issues](https://github.com/mrAbhimanyuVishwakarma/AxePower_Download/issues)
- **Chat:** [Discord](https://discord.gg/WfD4wZFJ8d)
- **Docs:** [Help Center](https://axepower.vercel.app/help.html)

## Author

Built by [Abhimanyu Vishwakarma](https://github.com/mrAbhimanyuVishwakarma). Releases are published in [AxePower_Download](https://github.com/mrAbhimanyuVishwakarma/AxePower_Download).

## License

MIT

<!-- TODO: The license is only stated in the badge. Add a LICENSE file to the repo (or link to it here) so the MIT terms are actually included. -->
