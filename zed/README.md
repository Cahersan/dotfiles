## Installation

Clone the repo and symlink the config into Zed's config directory:

```sh
git clone <repo-url> ~/dotfiles
ln -s ~/dotfiles/zed/keymap.json ~/.config/zed/keymap.json
ln -s ~/dotfiles/zed/settings.json ~/.config/zed/settings.json
```

If any of the files already exist, back them up or remove first. Zed reloads the keymap when the file is saved.

## Custom bindings

Some default Zed bindings clash with Vim mode or with my habits, so `keymap.json` rebinds them:

| Key | Context | Action | Replaces |
|---|---|---|---|
| `ctrl-s` | insert mode | Save file | Signature help |
| `ctrl-f` | insert and control modes | Search in buffer | Vim page down |
| `ctrl-b` | control modes | Toggle project panel | Vim page up |

I use the `pageup` and `pagedown` keys for page navigation, which is why `ctrl-f` and `ctrl-b` are free to rebind.

To debug a binding, open the key context view from the command palette and press the key. It lists every matching action and shows which one wins.

## Day-to-day commands

These are Vim and Zed commands I haven't committed 100% to muscle memory. Here for reference.

| Command | Definition |
|---|---|
| `ctrl-w w` / `ctrl-w W` | Focus next / previous pane |
| `ctrl-w p` | Focus previously active pane |
| `ctrl-w h/j/k/l` | Focus pane left / down / up / right |
| `ctrl-w v` / `ctrl-w s` | Split pane vertically / horizontally |
| `ctrl-w c` | Close current pane |
| `ctrl-o` / `ctrl-i` | Jump back / forward |
| `gs` | Go to symbol in file |
| `gS` | Go to symbol in project |
| `gd` | Go to definition |
| `ctrl-shift-v` | Open Markdown preview |
| `ctrl-p` | Search project files |
| `ctrl-shift-p` | Command palette |
