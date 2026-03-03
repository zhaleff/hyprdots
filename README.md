<h1 align="center">HollowSec's ZSH Alias Collection</h1>

<div align="center">
  <p>
    <a href="#"><img src="https://img.shields.io/badge/aliases-50+-blue?style=for-the-badge&logo=zsh&logoColor=white&labelColor=302D41&color=89B4FA" alt="Aliases"></a>&nbsp;&nbsp;
    <a href="#"><img src="https://img.shields.io/badge/last%20updated-2025--03--02-green?style=for-the-badge&logo=github&logoColor=white&labelColor=302D41&color=A6E3A1" alt="Last Updated"></a>&nbsp;&nbsp;
    <a href="#"><img src="https://img.shields.io/badge/license-MIT-yellow?style=for-the-badge&logo=open-source-initiative&logoColor=white&labelColor=302D41&color=F9E2AF" alt="License"></a>&nbsp;&nbsp;
    <a href="#"><img src="https://img.shields.io/badge/shell-ZSH-brightgreen?style=for-the-badge&logo=gnu-bash&logoColor=white&labelColor=302D41&color=CBA6F7" alt="Shell"></a>
  </p>
</div>

Hello.  This is my alias favourite for ZSH.  Over the years, I’ve accumulated a set of shortcuts that make daily terminal work faster, safer, and more enjoyable.  Each alias is carefully chosen to reduce keystrokes, prevent mistakes, and add a touch of personality to the command line.  Whether you’re managing packages, navigating the filesystem, or wrangling Git, these aliases will become second nature.

Let’s dive into the collection.

---

## Table of Contents
- [Pacman Aliases](#pacman-aliases)
- [File System Aliases](#file-system-aliases)
- [System & Workflow Aliases](#system--workflow-aliases)
- [Editor Aliases](#editor-aliases)
- [Git Aliases](#git-aliases)
- [Docker Aliases](#docker-aliases)
- [Development Aliases](#development-aliases)
- [Extract Function](#extract-function)

---

## Pacman Aliases
*For Arch Linux package management*

| Alias     | Command                          | Description                                      |
|-----------|----------------------------------|--------------------------------------------------|
| `pac`     | `sudo pacman`                    | Base pacman command with sudo                    |
| `pacupg`  | `sudo pacman -Syu`               | Full system upgrade                              |
| `pacin`   | `sudo pacman -S`                 | Install package(s)                               |
| `pacrem`  | `sudo pacman -Rns`               | Remove package(s) and dependencies               |
| `search`  | `pacman -Ss`                     | Search for packages                              |
| `cleanup` | `sudo pacman -Rns $(pacman -Qtdq); sudo pacman -Sc` | Remove orphans and clean cache |
| `yayupdate` | `yay -Syu`                     | Update AUR packages via yay                      |

These aliases save you from typing `sudo pacman` repeatedly and make routine maintenance a single word.

---

## File System Aliases
*Listing, navigating, and manipulating files*

| Alias | Command                                      | Description                                      |
|-------|----------------------------------------------|--------------------------------------------------|
| `ls`  | `exa --icons --color=always --group-directories-first` | List files with icons, directories first |
| `la`  | `exa -a --icons --color=always`              | List all files (including hidden)                |
| `ll`  | `exa -l --icons --color=always --git`         | Long listing with git status                     |
| `lla` | `exa -la --icons --color=always`              | Long listing including hidden                    |
| `tree`| `exa --tree --icons --color=always --level=3` | Tree view (3 levels deep)                        |
| `mkd` | `mkdir -pv`                                  | Create parent directories as needed              |
| `t`   | `touch`                                      | Create empty file(s)                             |
| `cp`  | `cp -iv`                                     | Copy interactively and verbosely                 |
| `mv`  | `mv -iv`                                     | Move interactively and verbosely                 |
| `rm`  | `rm -iv`                                     | Remove interactively and verbosely               |
| `shred` | `shred -u -z -n 5`                         | Securely delete file (overwrite + remove)        |
| `df`  | `df -hT`                                     | Disk usage in human‑readable format with FS type |
| `du`  | `du -h --max-depth=1`                         | Directory sizes, current level only              |
| `..`  | `cd ..`                                      | Go up one directory                              |
| `...` | `cd ../..`                                   | Go up two directories                            |
| `bat` | `bat --style=full`                            | Better `cat` with syntax highlighting            |

Why type `exa --icons` every time?  These aliases turn file listing into a pleasure.  The interactive flags on `cp`, `mv`, `rm` prevent accidental overwrites.

---

## System & Workflow Aliases
*Quick system commands and utilities*

| Alias    | Command                     | Description                                      |
|----------|-----------------------------|--------------------------------------------------|
| `cl`     | `clear`                     | Clear the terminal                               |
| `ff`     | `fastfetch`                 | Display system info (like neofetch but faster)   |
| `clock`  | `peaclock`                  | Terminal clock/stopwatch                         |
| `wf`     | `wf-recorder`               | Screen recording utility (Wayland)               |
| `win`    | `hyprctl clients`           | List open windows in Hyprland                    |
| `reboot` | `sudo reboot`               | Reboot the system                                |
| `shutdown` | `sudo shutdown now`       | Shut down immediately                            |
| `grep`   | `grep --color=auto -n`      | Grep with colour and line numbers                |
| `tailf`  | `tail -f`                   | Follow a log file                                |
| `ports`  | `ss -tulanp`                | Show listening ports and processes               |

These aliases wrap common admin and everyday commands.  `grep` with colour is so much easier to read.

---

## Editor Aliases
*Because you can't live without your text editor*

| Alias  | Command     | Description                                      |
|--------|-------------|--------------------------------------------------|
| `nn`   | `nano`      | Quick nano edit                                  |
| `vi`   | `vim`       | Vim (or Neovim, if symlinked)                    |
| `view` | `vim -R`    | Vim in read‑only mode                            |
| `code` | `code`      | VS Code (if installed)                           |

One‑letter or short aliases get you editing faster.

---

## Git Aliases
*Daily Git operations made tiny*

| Alias   | Command                     | Description                                      |
|---------|-----------------------------|--------------------------------------------------|
| `gs`    | `git status`                | Show working tree status                         |
| `ga`    | `git add`                   | Stage files                                      |
| `gc`    | `git commit -m`             | Commit with message                              |
| `gp`    | `git push`                  | Push to remote                                   |
| `gl`    | `git pull`                  | Pull from remote                                 |
| `gd`    | `git diff`                  | Show differences                                 |
| `gb`    | `git branch`                | List branches                                    |
| `gco`   | `git checkout`              | Switch branches or restore files                 |
| `glog`  | `git log --oneline --graph --decorate` | Compact, graphical log                  |
| `gcl`   | `git clone`                 | Clone a repository                               |
| `gstash`| `git stash`                 | Stash changes                                    |

These are the Git commands I use dozens of times a day.  `glog` is particularly beautiful.

---

## Docker Aliases
*Container management shortcuts*

| Alias | Command                | Description                                      |
|-------|------------------------|--------------------------------------------------|
| `dps` | `docker ps`            | List running containers                          |
| `dim` | `docker images`        | List images                                      |
| `dcu` | `docker compose up -d` | Start services in detached mode                  |
| `dcd` | `docker compose down`  | Stop and remove containers                       |
| `dcl` | `docker compose logs -f` | Follow logs of compose services                 |

Docker Compose commands are now three letters instead of a mouthful.

---

## Development Aliases
*For Python, Firebase, and fun*

| Alias     | Command                                      | Description                                      |
|-----------|----------------------------------------------|--------------------------------------------------|
| `py`      | `python3`                                    | Python 3                                         |
| `pip`     | `pip3`                                       | Pip for Python 3                                 |
| `venv`    | `python3 -m venv .venv && source .venv/bin/activate` | Create and activate a virtual environment |
| `fd`      | `firebase deploy`                            | Deploy to Firebase                               |
| `yt`      | `yt-dlp`                                     | Download videos from YouTube etc.                 |
| `weather` | `curl wttr.in/~Madrid`                       | Weather for Madrid (change city as needed)       |
| `matrix`  | `cmatrix -b`                                 | The iconic Matrix rain                           |

`venv` is a lifesaver for Python projects—one command sets up and activates a virtual environment.

---

## Extract Function
*A universal archive extractor*

Not an alias, but a handy function included in the config:

```bash
extract() {
  if [ -f "$1" ]; then
    case $1 in
      *.tar.bz2)  tar xjf $1 ;;
      *.tar.gz)   tar xzf $1 ;;
      *.bz2)      bunzip2 $1 ;;
      *.rar)      unrar x $1 ;;
      *.gz)       gunzip $1 ;;
      *.tar)      tar xf $1 ;;
      *.tbz2)     tar xjf $1 ;;
      *.tgz)      tar xzf $1 ;;
      *.zip)      unzip $1 ;;
      *.Z)        uncompress $1 ;;
      *.7z)       7z x $1 ;;
      *)          echo "'$1' cannot be extracted" ;;
    esac
  else
    echo "'$1' is not a valid file"
  fi
}

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
