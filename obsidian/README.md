## Installation

Obsidian has no settings shared across vaults. To use a snippet in a vault, either symlink or copy it into the vault's snippets folder:

```sh
mkdir -p ~/path/to/vault/.obsidian/snippets
ln -s ~/dotfiles/obsidian/snippets/reading.css ~/path/to/vault/.obsidian/snippets/
# or
cp ~/dotfiles/obsidian/snippets/reading.css ~/path/to/vault/.obsidian/snippets/
```

Then enable it in **Settings → Appearance → CSS snippets**.

- **Symlink**: edits in this repo reach the vault, but Obsidian only notices them after **Reload app without saving** (command palette) or toggling the snippet off and on.
- **Copy**: edits in the vault apply live, but the copy drifts from this repo. Copy it back here when you change it.
