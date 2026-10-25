## Installation

Requires tmux 3.1 or newer (for the `~/.config/tmux` path). Clone the repo, symlink the config and install [TPM](https://github.com/tmux-plugins/tpm), the plugin manager:

```sh
git clone <repo-url> ~/dotfiles
mkdir -p ~/.config/tmux
ln -s ~/dotfiles/tmux/tmux.conf ~/.config/tmux/tmux.conf
git clone https://github.com/tmux-plugins/tpm ~/.config/tmux/plugins/tpm
```

Then start tmux and press `prefix I` to download the plugins. If tmux was already running, reload the config first with `tmux source ~/.config/tmux/tmux.conf`.

If `~/.tmux.conf` exists, remove it: tmux reads it before the XDG path.

On Wayland, install `wl-clipboard` (`sudo apt install wl-clipboard`) so `tmux-yank` can copy to the system clipboard and middle click can paste the primary selection. Without it, copying still works in terminals that support OSC 52, and middle click pastes nothing in shell panes.

## Configuration

Main changes from stock tmux:

- **Prefix is `ctrl-a`** instead of `ctrl-b`. Press `ctrl-a ctrl-a` to send `ctrl-a` to the shell (go to start of line).
- **Mouse on**: click to focus panes and windows, drag borders to resize, scroll to enter copy mode, drag to select. A mouse selection goes to the primary selection (paste with middle click), like in other Linux apps; press `y` afterwards to also copy it to the clipboard.
- **Vi copy mode** with `v` to select and `y` to yank to the system clipboard.
- **Middle click pastes the primary selection**, the text last selected in any app (e.g. Zed), like everywhere else on Linux. Stock tmux pastes its own buffer instead. Apps that handle the mouse themselves, like Claude Code or Vim, get the click unchanged.
- **Vim-style navigation**: `h/j/k/l` to move between panes, `H/J/K/L` to resize them.
- **Intuitive splits**: `|` and `-`. Splits and new windows keep the current directory.
- **Windows and panes numbered from 1**, renumbered when one is closed.
- **True color, focus events and no Escape delay**, so editors inside tmux behave as they do outside.
- **Minimal status bar** showing the session name, windows, the time and a `PREFIX` indicator while the prefix is pressed. It uses named colors (`cyan`, `white`) and the default background, so it follows the terminal's color scheme.

Plugins:

| Plugin | Purpose |
|---|---|
| [tpm](https://github.com/tmux-plugins/tpm) | Plugin manager |
| [tmux-sensible](https://github.com/tmux-plugins/tmux-sensible) | Defaults nearly everyone agrees on |
| [tmux-yank](https://github.com/tmux-plugins/tmux-yank) | Copy to the system clipboard |
| [tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect) | Save and restore sessions, windows, panes, directories and pane contents |
| [tmux-continuum](https://github.com/tmux-plugins/tmux-continuum) | Save every 15 minutes and restore on start, so sessions survive a reboot |

## Day-to-day commands

All bindings start with the prefix (`ctrl-a`), shown as `prefix`. Press and release it, then the key.

| Command | Definition |
|---|---|
| `tmux new -s name` | Start a new session called `name` |
| `tmux ls` | List sessions |
| `tmux a` / `tmux a -t name` | Attach to the last / a named session |
| `prefix d` | Detach from the session (it keeps running) |
| `prefix s` | Pick a session from a tree |
| `prefix $` | Rename session |
| `prefix c` | New window |
| `prefix ,` | Rename window |
| `prefix n` / `prefix p` | Next / previous window |
| `prefix 1..9` | Go to window by number |
| `prefix w` | Pick a window from a tree |
| `prefix \|` / `prefix -` | Split side by side / stacked |
| `prefix h/j/k/l` | Focus pane left / down / up / right |
| `prefix H/J/K/L` | Resize pane (repeatable) |
| `prefix z` | Zoom pane to full window and back |
| `prefix x` / `prefix &` | Close pane / window |
| `prefix space` | Cycle pane layouts |
| `prefix [` | Enter copy mode (scroll with the mouse also works) |
| `v` / `ctrl-v` / `y` | In copy mode: select / block select / copy to the clipboard |
| `q` | Leave copy mode |
| `prefix ]` | Paste tmux buffer |
| `prefix r` | Reload config |
| `prefix I` / `prefix U` | Install / update plugins |
| `prefix ctrl-s` / `prefix ctrl-r` | Save / restore sessions manually |
| `prefix ctrl-a` | Send `ctrl-a` to the program in the pane |
| `prefix ?` | List all key bindings |

Hold `shift` while selecting with the mouse to bypass tmux and use the terminal's own selection.
