<h1 align="center">
  <img src="Assets/desktop.png" alt="BlackNode Desktop" width="100%"/>
</h1>

<div align="center">
  <a href="https://github.com/zhaleff/BlackNode/stargazers"><img src="https://img.shields.io/github/stars/zhaleff/BlackNode?style=for-the-badge&logo=starship&color=C9CBFF&logoColor=C9CBFF&labelColor=302D41" alt="stars"></a>&nbsp;&nbsp;
  <a href="https://github.com/zhaleff/BlackNode/forks"><img src="https://img.shields.io/github/forks/zhaleff/BlackNode?style=for-the-badge&logo=git&logoColor=f9e2af&label=Forks&labelColor=302D41&color=f9e2af" alt="forks"></a>&nbsp;&nbsp;
  <a href="https://github.com/zhaleff/BlackNode/issues"><img src="https://img.shields.io/github/issues/zhaleff/BlackNode?style=for-the-badge&logo=github&logoColor=eba0ac&label=Issues&labelColor=302D41&color=eba0ac" alt="issues"></a>&nbsp;&nbsp;
  <a href="https://github.com/zhaleff/BlackNode/commits/main"><img src="https://img.shields.io/github/last-commit/zhaleff/BlackNode?style=for-the-badge&logo=github&logoColor=white&label=Last%20Commit&labelColor=302D41&color=A6E3A1" alt="last commit"></a>&nbsp;&nbsp;
  <a href="https://github.com/zhaleff/BlackNode/blob/main/LICENSE"><img src="https://img.shields.io/github/license/zhaleff/BlackNode?style=for-the-badge&logo=open-source-initiative&color=CBA6F7&logoColor=CBA6F7&labelColor=302D41" alt="license"></a>&nbsp;&nbsp;
  <a href="https://discord.gg/hollowsec"><img src="https://img.shields.io/badge/chat-discord-5865F2?style=for-the-badge&logo=discord&logoColor=white&labelColor=302D41" alt="discord"></a>
</div>

#

<div align="center">
  &ensp;<a href="./INSTALLATION.md"><kbd> <br> Installation <br> </kbd></a>&ensp;
  &ensp;<a href="./KEYBINDS.md"><kbd> <br> Keybindings <br> </kbd></a>&ensp;
  &ensp;<a href="./MODULES.md"><kbd> <br> Modules <br> </kbd></a>&ensp;
  &ensp;<a href="./WAYBAR.md"><kbd> <br> Waybar <br> </kbd></a>&ensp;
  &ensp;<a href="./REFERENCE.md"><kbd> <br> Reference <br> </kbd></a>&ensp;
  &ensp;<a href="./HollowSec.md"><kbd> <br> HollowSec <br> </kbd></a>&ensp;
</div>

#

<div align="center">
  <h3>Your home in the terminal. Simple, clean, yours.</h3>
  <p><i>Dotfiles that embrace, not complicate.</i></p>
</div>

#

## Hello.

This is my personal Linux configuration. BlackNode is a collection of dotfiles that grew from years of tweaking, breaking, and slowly understanding what makes a system feel like home. It is not a monolithic rice that you copy and forget. It is a living set of files, each one written to be read, understood, and eventually changed by you.

My first dotfiles were horrible. They were messy, inconsistent, and half of them did not even work. But I kept at it, and over time they became something I was proud to share. BlackNode is that pride, packaged up and offered to you with one wish: take it, make it your own, and in doing so discover that you are capable of far more than you think.

#

## Showcase

<div align="center">

<div align="center">
  <img src="Assets/desktop.png" width="49%" alt="Desktop"/>
  <img src="Assets/fastfetch.png" width="49%" alt="Fastfetch"/>
</div>

<br>

<div align="center">
  <img src="Assets/hyprlock.png" width="49%" alt="Hyprlock"/>
  <img src="Assets/wlogout.png" width="49%" alt="Wlogout"/>
</div>

<br>

<div align="center">
  <img src="Assets/rofi.png" width="32%" alt="Rofi"/>
  <img src="Assets/rofi_2.png" width="32%" alt="Rofi 2"/>
  <img src="Assets/rofi_3.png" width="32%" alt="Rofi 3"/>
</div>

<br>

<div align="center">
  <img src="Assets/rofi_5.png" width="49%" alt="Rofi 5"/>
  <img src="Assets/rofi_8.png" width="49%" alt="Rofi 8"/>
</div>

<br>

<div align="center">
  <img src="Assets/wallselect.png" width="80%" alt="Wallpaper Selector"/>
</div>

</div>

#

## What is Inside?

BlackNode brings together a deliberate stack of tools that work in harmony. Every tool was chosen for a reason. Nothing is here just because it is popular.

| Component | Tool | Role |
|---|---|---|
| Window Manager | Hyprland | Dynamic tiling Wayland compositor |
| Status Bar | Waybar | Fully configurable bar with multiple styles |
| Terminal | Kitty + Alacritty | GPU-accelerated terminal emulators |
| Shell | Zsh + Powerlevel10k | Fast shell with a powerful, informative prompt |
| Launcher | Rofi | App launcher, window switcher and dmenu replacement |
| Notifications | Dunst | Lightweight and clean notification daemon |
| Lockscreen | Hyprlock + Hypridle | GPU-accelerated lock screen with idle management |
| File Manager | Yazi | Blazing-fast terminal file manager written in Rust |
| Editor | Neovim | Extensible modal text editor |
| Theming | Wallust | Generates full colour schemes from your wallpaper |
| Wallpaper Daemon | awww | GPU-accelerated Wayland wallpaper daemon |
| Clipboard | Clipse | Persistent clipboard history manager for Wayland |
| Audio Visualiser | Cava | Terminal-based audio visualiser |
| Logout Screen | Wlogout | Clean and configurable session management screen |
| System Info | Fastfetch | Fast, customisable system information tool |
| AUR Helper | yay | AUR package manager built on top of pacman |

#

## Installation

#

### Quick install

Clone the repository into your home directory and run the main installer. That is all you need to do to get started.

```bash
git clone https://github.com/zhaleff/BlackNode.git $HOME/BlackNode
cd $HOME/BlackNode
bash blacknode.sh
```

`blacknode.sh` is the entry point for BlackNode. It will walk you through the setup interactively and call individual component scripts based on your choices. You decide what gets installed — nothing runs without your input.

#

### Manual install

Every script in BlackNode is fully independent. You can run any of them on their own, in any order, without going through `blacknode.sh` at all. This is the recommended approach if you want to cherry-pick only what you need.

If you do not have an AUR helper yet, start here:

```bash
bash yay.sh
```

Then run whatever components you want:

```bash
# Documentation — informational only, no side effects
bash welcome.sh
bash introduction.sh
bash information.sh
bash changelog.sh
bash help.sh

# Core
bash flatpak.sh
bash bins.sh
bash update.sh

# Window Manager
bash hyprland.sh
bash hyprlock.sh
bash hyprshot.sh

# Bar & Launcher
bash waybar.sh
bash rofi.sh

# Terminal & Shell
bash kitty.sh
bash alacritty.sh
bash zsh.sh

# Tools
bash nvim.sh
bash yazi.sh
bash fastfetch.sh
bash cava.sh
bash clipse.sh
bash dunst.sh
bash wlogout.sh

# Theming
bash wallust.sh
bash wallpaper.sh
bash gtk.sh
bash awww.sh
```

For a complete breakdown of what every script does, see [INSTALLATION.md](./INSTALLATION.md).

#

## Repository Structure

```
$HOME/BlackNode/
├── blacknode.sh                  ← main installer, start here
├── yay.sh
├── hyprland.sh
├── hyprlock.sh
├── hyprshot.sh
├── waybar.sh
├── rofi.sh
├── kitty.sh
├── alacritty.sh
├── zsh.sh
├── nvim.sh
├── yazi.sh
├── fastfetch.sh
├── cava.sh
├── clipse.sh
├── dunst.sh
├── wlogout.sh
├── wallust.sh
├── wallpaper.sh
├── gtk.sh
├── awww.sh
├── flatpak.sh
├── bins.sh
├── update.sh
├── welcome.sh
├── introduction.sh
├── information.sh
├── changelog.sh
├── help.sh
│
├── Assets/
│   ├── desktop.png
│   ├── fastfetch.png
│   ├── hyprlock.png
│   ├── rofi.png
│   ├── rofi_2.png
│   ├── rofi_3.png
│   ├── rofi_5.png
│   ├── rofi_8.png
│   ├── wallselect.png
│   └── wlogout.png
│
└── Configs/
    ├── .config/
    │   ├── hypr/
    │   ├── waybar/
    │   ├── kitty/
    │   ├── alacritty/
    │   ├── nvim/
    │   ├── rofi/
    │   ├── dunst/
    │   ├── zsh/
    │   ├── powerlevel10k/
    │   ├── yazi/
    │   ├── fastfetch/
    │   ├── cava/
    │   ├── clipse/
    │   ├── wallust/
    │   ├── wlogout/
    │   ├── gtk-3.0/
    │   ├── gtk-4.0/
    │   ├── qt5ct/
    │   └── sddm/
    └── .local/
        └── bin/
```

#

## Documentation

Each major aspect of BlackNode has its own dedicated document. Use the buttons at the top to jump to them, or open the files directly.

| Document | Content |
|---|---|
| [INSTALLATION.md](./INSTALLATION.md) | Full step-by-step guide — every script explained in detail |
| [KEYBINDS.md](./KEYBINDS.md) | Every Hyprland keybinding, documented and organised |
| [MODULES.md](./MODULES.md) | Deep dive into Waybar modules and what each one does |
| [WAYBAR.md](./WAYBAR.md) | Available Waybar styles and how to switch between them |
| [REFERENCE.md](./REFERENCE.md) | Sources, inspiration and how to build your own dotfiles |
| [HollowSec.md](./HollowSec.md) | The community behind BlackNode |

#

## The HollowSec Community

BlackNode is maintained by [zhaleff](https://github.com/zhaleff) and supported by the **HollowSec** community — a group of people passionate about cybersecurity, programming, and building cool things together. We believe in learning by doing, sharing knowledge freely, and lifting each other up.

If you want to chat, ask questions, or just hang out with people who get it, join us: [discord.gg/hollowsec](https://discord.gg/hollowsec).

#

## A Word to You

I have been where you are. I have stared at other people's dotfiles, overwhelmed by the complexity, convinced I could never create something like that. But I started small. I copied one line, then another. I broke things and fixed them. And slowly, it became mine.

You can do this. You are capable of more than you know. All it takes is the courage to start, the patience to learn from mistakes, and the belief that you belong here.

BlackNode is not the answer. It is just a starting point. The real answer is inside you.

Now go. Explore. Break things. Fix them. And make this your own.

#

## Licence

BlackNode is released under the [MIT Licence](./LICENSE). You are free to use, modify, and share it however you wish. Attribution is appreciated but not required.

#

<div align="center">
  <p>Made with ❤️ by <a href="https://github.com/zhaleff">zhaleff</a> and the HollowSec community.</p>
  <p>Happy hacking.</p>
</div>
