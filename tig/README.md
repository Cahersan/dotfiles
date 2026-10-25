## Installation

Clone the repo and symlink the config into tig's config directory:

```sh
git clone <repo-url> ~/dotfiles
mkdir -p ~/.config/tig
ln -s ~/dotfiles/tig/config ~/.config/tig/config
```

If `~/.tigrc` exists, remove it: tig reads it instead of the XDG path.

## Configuration

Only colors for now. tig draws the selected line and the title bar as white text on green and blue, which is unreadable with the light green and blue of the [Alacritty](../alacritty) palette. The config switches them to dark text.

## Day-to-day commands

| Command | Definition |
|---|---|
| `tig` | Commit log of the current branch |
| `tig status` | Stage and unstage changes, like `git add -p` |
| `tig blame file` | Blame view of a file |
| `j` / `k` | Move down / up |
| `enter` | Open the selected commit or file |
| `q` | Close the current view (quits on the last one) |
| `u` | In status view: stage / unstage file or chunk |
| `C` | In status view: commit |
| `/` | Search |
| `h` | List all key bindings |
