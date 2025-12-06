# My Tmux Configuration

This is my personal `tmux` configuration, customized from the excellent [Oh my tmux!](https://github.com/gpakosz/.tmux) by Gregory Pakosz.

## Features

- **Base**: built on top of `gpakosz/.tmux`.
- **Theme**: Custom color scheme (dark/gray scale with highlights).
- **CPU Monitor**: Custom `cpu_graph` function for the status bar showing:
  - Usage intensity with Emojis (❄️, ☀️, 🔥)
  - Visual bar graph (e.g., ` ▂▃▄▅▆▇█`)
- **Plugins**: Includes `tmux-plugins/tmux-cpu`.

## Screenshot
<img width="1512" height="37" alt="截圖 2025-12-06 18 24 08" src="https://github.com/user-attachments/assets/848ca21b-c4fc-4e02-8770-08ad265dbd8b" />
<img width="1512" height="41" alt="截圖 2025-12-06 18 23 51" src="https://github.com/user-attachments/assets/54deb058-ab58-446b-a613-e77aa97973e6" />
<img width="1512" height="39" alt="截圖 2025-12-06 18 23 42" src="https://github.com/user-attachments/assets/54bce981-7c79-4b5e-a6e0-b6d3627a3d4f" />


## Installation

1.  Clone this repository to your tmux configuration directory:

    ```bash
    git clone https://github.com/yourusername/tmux-config.git ~/.config/tmux
    ```

2.  Create a symlink for `tmux.conf` if it doesn't exist (or launch tmux with `-f`):

    ```bash
    ln -s ~/.config/tmux/tmux.conf ~/.tmux.conf
    ln -s ~/.config/tmux/tmux.conf.local ~/.tmux.conf.local
    ```

    *Note: If you are using the XDG Config Home structure (default for this repo location), tmux 3.2+ should automatically pick up `~/.config/tmux/tmux.conf`.*

## Requirements

- **tmux** (version 3.2 or higher recommended)
- **macOS** (The custom CPU script uses `sysctl` which is specific to macOS/BSD. Modifications required for Linux).
- **Fonts**: A terminal font that supports standard Unicode/Nerd Fonts is recommended for the best experience with the status bar symbols.

## Customization

The main logic resides in `tmux.conf.local`. You can tweak the colors, bindings, and the `cpu_graph` script directly in that file.

### CPU Graph Script
The custom CPU usage script located at the bottom of `tmux.conf.local` adapts to your system's load:
- **Low Load**: ❄️
- **Medium Load**: ☀️
- **High Load**: 🔥
