## Installation

Clone the repo and symlink the config into Alacritty's config directory:

```sh
git clone <repo-url> ~/dotfiles
mkdir -p ~/.config/alacritty
ln -s ~/dotfiles/alacritty/alacritty.toml ~/.config/alacritty/alacritty.toml
```

Alacritty reloads the config when the file is saved.

## Configuration

Made to look like Zed, so the editor and terminal feel the same:

- **Font**: [JetBrains Mono](https://www.jetbrains.com/lp/mono/) at 11pt. Alacritty sizes fonts in points, Zed in pixels, so the numbers don't match between the two. Install it with `sudo apt install fonts-jetbrains-mono`.
- **Line spacing**: 3 extra pixels per line, roughly matching Zed's line height.
- **Colors**: the dark gray background of One Dark, Zed's default dark theme, with brighter accents inspired by Ayu Dark for contrast. tmux uses these colors too.
- **Padding** of 10px around the text, and the mouse pointer hides while typing.

Alacritty has no tabs or splits on purpose: [tmux](../tmux) handles that.

To tweak the look:

| Setting | Key |
|---|---|
| Font family and size | `font.normal.family`, `font.size` |
| Line spacing | `font.offset.y` (keep `font.glyph_offset.y` at about half of it) |
| Background color | `colors.primary.background` |

## Day-to-day commands

| Command | Definition |
|---|---|
| `ctrl-shift-c` / `ctrl-shift-v` | Copy / paste |
| `ctrl-+` / `ctrl--` / `ctrl-0` | Bigger / smaller / reset font size |
| `ctrl-shift-n` | New window |
| `ctrl-shift-space` | Alacritty's own vi mode (rarely needed inside tmux) |
