<h1 align="center">HollowSec's Waybar Modules</h1>

<div align="center">
  <p>
    <a href="#"><img src="https://img.shields.io/badge/modules-19-blue?style=for-the-badge&logo=wayland&logoColor=white&labelColor=302D41&color=89B4FA" alt="Modules"></a>&nbsp;&nbsp;
    <a href="#"><img src="https://img.shields.io/badge/last%20updated-2025--03--02-green?style=for-the-badge&logo=github&logoColor=white&labelColor=302D41&color=A6E3A1" alt="Last Updated"></a>&nbsp;&nbsp;
    <a href="#"><img src="https://img.shields.io/badge/license-MIT-yellow?style=for-the-badge&logo=open-source-initiative&logoColor=white&labelColor=302D41&color=F9E2AF" alt="License"></a>&nbsp;&nbsp;
    <a href="#"><img src="https://img.shields.io/badge/Waybar-0.9.24+-brightgreen?style=for-the-badge&logo=files&logoColor=white&labelColor=302D41&color=CBA6F7" alt="Waybar"></a>
  </p>
</div>

Hello.  This document describes the modules used in my primary Waybar configuration.  Each module is grouped logically on the bar, and every element has been chosen to provide essential information at a glance while remaining visually clean.  The configuration is designed for Hyprland on Arch Linux, but many modules are desktop‑agnostic.

Below you’ll find an explanation of each group and its constituent modules, along with notes on their behaviour and customisation.

---

## Table of Contents
- [Left Side Groups](#left-side-groups)
  - [group/hollow-left-2 – Workspaces](#grouphollow-left-2--workspaces)
  - [group/hollow-left-4 – Media Controls](#grouphollow-left-4--media-controls)
  - [group/hollow-left-5 – System Tray & Hardware](#grouphollow-left-5--system-tray--hardware)
  - [group/hollow-left-1 – Package Updates](#grouphollow-left-1--package-updates)
- [Right Side Groups](#right-side-groups)
  - [group/hollow-right-5 – Active Window](#grouphollow-right-5--active-window)
  - [group/hollow-right-4 – Idle Inhibitor & Clock](#grouphollow-right-4--idle-inhibitor--clock)
  - [group/hollow-right-1 – System Resources](#grouphollow-right-1--system-resources)
  - [group/hollow-right-3 – User Info](#grouphollow-right-3--user-info)
- [Module Reference](#module-reference)

---

## Left Side Groups

### group/hollow-left-2 – Workspaces
**Modules:** `hyprland/workspaces`

This group contains only the workspace module for Hyprland.  It displays the names or icons of available workspaces, with visual distinction for the active workspace and urgent windows.

| Module | Description | Key Configuration |
|--------|-------------|-------------------|
| `hyprland/workspaces` | Shows all workspaces. Click to switch. Active workspace uses icon `󰮯`; others use `*`. | `all-outputs: true` – shows workspaces from all monitors. `persistent_workspaces` ensures at least three workspaces are always shown. |

---

### group/hollow-left-4 – Media Controls
**Modules:** `mpris`, `custom/previous`, `custom/pause`, `custom/next`

A compact media player controller that integrates with MPRIS‑compatible players (Spotify, Firefox, etc.).

| Module | Description | Interaction |
|--------|-------------|-------------|
| `mpris` | Displays currently playing song title and artist. Shows player‑specific icons (Spotify, Firefox) and a paused state indicator. | Hover for tooltip with full details. |
| `custom/previous` | Icon to skip to previous track. | Click sends `previous` command to Spotify and YouTube Music. |
| `custom/pause` | Play/pause toggle. Icon changes between `` (play) and `` (pause). | Click toggles play state for Spotify. |
| `custom/next` | Icon to skip to next track. | Click sends `next` command to Spotify and YouTube Music. |

---

### group/hollow-left-5 – System Tray & Hardware
**Modules:** `backlight`, `wireplumber`, `network`, `custom/power`, `battery`

This group brings together hardware status indicators and the power menu.

| Module | Description | Interaction |
|--------|-------------|-------------|
| `backlight` | Screen brightness level, shown as an icon that changes with brightness. | No click action defined; purely informational. |
| `wireplumber` | Audio volume level with mute indication. Icons change with volume. | No click action (can be added). |
| `network` | Network status – Wi‑Fi signal strength or Ethernet IP. Disconnected shows `󰖪`. | Click opens a custom RoFi Wi‑Fi menu script. |
| `custom/power` | Power button icon. | Click launches `wlogout` for session control. |
| `battery` | Battery percentage and charging status. Icons represent charge level. | Hover shows remaining time. |

---

### group/hollow-left-1 – Package Updates
**Modules:** `custom/pacman`, `custom/pkg-aur`

Two modules that display the number of available updates from official repositories and the AUR.

| Module | Description | Interaction |
|--------|-------------|-------------|
| `custom/pacman` | Shows count of official package updates (from `checkupdates`). | Click opens a terminal and runs `sudo pacman -Syu`. |
| `custom/pkg-aur` | Shows count of AUR package updates (from `yay -Qua`). | Purely informational; no click action. |

---

## Right Side Groups

### group/hollow-right-5 – Active Window
**Modules:** `hyprland/window`

A single module that displays the title of the currently focused window.

| Module | Description | Notes |
|--------|-------------|-------|
| `hyprland/window` | Shows window title, truncated to 32 characters. Prefixed with `󰶞`. | `separate-outputs: false` – shows the window on the current output. |

---

### group/hollow-right-4 – Idle Inhibitor & Clock
**Modules:** `idle_inhibitor`, `clock`

Two small modules for time and idle management.

| Module | Description | Interaction |
|--------|-------------|-------------|
| `idle_inhibitor` | Toggles whether the system can idle/suspend. Icon changes: `󰛊` (inactive) / `󰅶` (active). | Click toggles inhibitor. |
| `clock` | Shows current time in `HH:MM` format. | Hover shows full calendar. Click (or `format-alt`) shows date. |

---

### group/hollow-right-1 – System Resources
**Modules:** `cpu`, `temperature`, `memory`

Real‑time system resource usage.

| Module | Description | Interaction |
|--------|-------------|-------------|
| `cpu` | CPU usage percentage, prefixed with ``. | Click opens `btop` in a Kitty terminal. |
| `temperature` | CPU temperature (from thermal zone 2). Shows `` icon. Critical threshold at 80°C. | Click opens `btop`. |
| `memory` | RAM usage percentage, prefixed with ``. | No click action. |

---

### group/hollow-right-3 – User Info
**Modules:** `custom/user`

Displays the current username.

| Module | Description | Interaction |
|--------|-------------|-------------|
| `custom/user` | Shows `whoami` output, prefixed with ``. | Click sends a notification with `whoami@hostname`. |

---

## Module Reference

Below is a quick reference of all modules used in the configuration, including those that are part of groups and any standalone modules (though none are placed outside groups in this config).

| Module Name | Purpose | Group |
|-------------|---------|-------|
| `hyprland/workspaces` | Workspace switcher | left-2 |
| `mpris` | Now playing info | left-4 |
| `custom/previous` | Previous track | left-4 |
| `custom/pause` | Play/pause | left-4 |
| `custom/next` | Next track | left-4 |
| `backlight` | Screen brightness | left-5 |
| `wireplumber` | Audio volume | left-5 |
| `network` | Network status | left-5 |
| `custom/power` | Power menu | left-5 |
| `battery` | Battery status | left-5 |
| `custom/pacman` | Official package updates | left-1 |
| `custom/pkg-aur` | AUR package updates | left-1 |
| `hyprland/window` | Active window title | right-5 |
| `idle_inhibitor` | Idle inhibition toggle | right-4 |
| `clock` | Time and date | right-4 |
| `cpu` | CPU usage | right-1 |
| `temperature` | CPU temperature | right-1 |
| `memory` | RAM usage | right-1 |
| `custom/user` | Username display | right-3 |

*Note: Some modules like `tray`, `bluetooth`, `disk`, `custom/public-ip`, `custom/htb-vpn` are defined in the configuration but not currently placed in any group.  They can be added to groups as desired.*

---

## Final Thoughts

This module set balances essential system information with media controls and aesthetic simplicity.  Each module is configured to be unobtrusive yet functional, and the grouping keeps the bar organised.  Feel free to adapt the groups or add new modules to suit your own workflow.

If you have questions or suggestions, please reach out.

**— HollowSec**


<h1 align="center">ZepharDev </h1>

<p align="center">
  <a href="https://github.com/ZepharDev/hyprdots/stargazers">
    <img src="https://img.shields.io/github/stars/ZepharDev/hyprdots?color=cba6f7&style=for-the-badge&label=Stars&labelColor=1e1e2e&logo=starship&logoColor=white" style="margin: 0 10px;">
  </a>
  <a href="https://github.com/ZepharDev/hyprdots/network/members">
    <img src="https://img.shields.io/github/forks/ZepharDev/hyprdots?color=cba6f7&style=for-the-badge&label=Forks&labelColor=1e1e2e&logo=sourcetree&logoColor=white" style="margin: 0 10px;">
  </a>
  <a href="https://github.com/ZepharDev/hyprdots/commits">
    <img src="https://img.shields.io/github/commit-activity/y/ZepharDev/hyprdots?color=eba0ac&style=for-the-badge&label=Commits&labelColor=1e1e2e&logo=git&logoColor=white" style="margin: 0 10px;">
  </a>
  <a href="https://github.com/ZepharDev/hyprdots/commits">
    <img src="https://img.shields.io/github/last-commit/ZepharDev/hyprdots?color=f9e2af&style=for-the-badge&label=Last%20Commit&labelColor=1e1e2e&logo=clockify&logoColor=white" style="margin: 0 10px;">
  </a>
</p>

<h1 align="center">🍂 Wlogout</h1> 

<img width="1366" height="768" alt="2025-07-20-163910_hyprshot" src="https://github.com/user-attachments/assets/d08b163a-07e7-4ea1-8896-c77a302dd92c" />

<h1 align="center">🌴 Rofi</h1>

<img width="1366" height="768" alt="2025-07-17-203951_hyprshot" src="https://github.com/user-attachments/assets/11d291ae-f510-4306-9434-11ac7c1868d3" />

<h1 align="center">🍁 Cava & peaclock</h1>

<img width="1366" height="768" alt="2025-07-22-213450_hyprshot" src="https://github.com/user-attachments/assets/7d1941cf-213f-49c0-97a0-96af894a63ac" />

<h1 align="center">🗝️ Music Player Menu rofi</h1>

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/cbbe8f2d-2f13-40d9-a99c-17b13356366e" />


<h1 align="center">🌻 Hyprlock</h1>

<img width="854" height="475" alt="2025-07-19-112108_hyprshot" src="https://github.com/user-attachments/assets/cf2569ca-99c2-42d1-b28d-f2f13c2db7ca" />

<h1 align="center">☃️ FastFetch</h1>

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/2f45dce9-1c62-457f-a8e4-4af6e78caf93" />

<h1 align="center">❄️ Hyprshot Menu</h1>

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/a015aabd-07ad-46de-bdfa-51933d2d29e1" />

<h1 align="center">🌊 SwayNC</h1>

<img width="1366" height="768" alt="2025-07-13-111730_hyprshot" src="https://github.com/user-attachments/assets/eaf172b5-0474-40c1-913b-f3588b5c928f" />

<h1 align="center">🌪️ Power Menu</h1>

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7179b1c7-1f93-4c18-a135-6b9d59ba2b15" />

---

<div align="center">
  <p>
    <img src="https://img.shields.io/badge/Built_with-Hyprland-cba6f7?style=for-the-badge&logo=hyprland&logoColor=white&labelColor=1e1e2e" />
    <img src="https://img.shields.io/badge/Powered_by-Arch_Linux-f5c2e7?style=for-the-badge&logo=arch-linux&logoColor=white&labelColor=1e1e2e" />
    <img src="https://img.shields.io/badge/Crafted_by-ZepharDev-f9e2af?style=for-the-badge&logo=github&logoColor=white&labelColor=1e1e2e" />
  </p>

<div align="center">
  <p>
    <img src="https://img.shields.io/badge/✝%20Christ_First-eba0ac?style=for-the-badge&labelColor=1e1e2e&logoColor=white" />
    <img src="https://img.shields.io/badge/✟%20Soli_Deo_Gloria-cba6f7?style=for-the-badge&labelColor=1e1e2e&logoColor=white" />
    <img src="https://img.shields.io/badge/☧%20Faith-f5c2e7?style=for-the-badge&labelColor=1e1e2e&logoColor=white" />
  </p>
  <p>
    <sub>Code and craft — for Christ alone. YHWH reigns.</sub>
  </p>
</div>

<details>
  <summary><strong>🖼️ Showcase Gallery</strong></summary>  <table>
    <tr>
      <td><
