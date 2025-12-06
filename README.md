# My Tmux Configuration

This is my personal `tmux` configuration, customized from the excellent [Oh my tmux!](https://github.com/gpakosz/.tmux) by Gregory Pakosz.

## Features

- **Base**: built on top of `gpakosz/.tmux`.
- **Theme**: Custom color scheme (dark/gray scale with highlights).
- **CPU Monitor**: Custom `cpu_graph` function for the status bar showing:
  - Usage intensity with Emojis (❄️, ☀️, 🔥)
  - Visual bar graph (e.g., ` ▂▃▄▅▆▇█`)
- **Plugins**: Includes `tmux-plugins/tmux-cpu`.

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
