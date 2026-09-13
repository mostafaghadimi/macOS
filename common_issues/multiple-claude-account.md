# Running Multiple Claude Accounts on macOS

Each account = its own config directory. Log in once per directory, then it stays logged in.
Replace `<name>` below with a label for the extra account (e.g. `work`, `personal`).

---

## Desktop App

```bash
osacompile -o "/Applications/Claude <name>.app" -e 'do shell script "open -n -a \"/Applications/Claude.app\" --args --user-data-dir=\"$HOME/Library/Application Support/Claude-<name>\" > /dev/null 2>&1 &"'
```
Builds a "Claude \<name\>" launcher app that opens Claude with a separate data dir.
Example: `osacompile -o "/Applications/Claude Work.app" -e 'do shell script "open -n -a \"/Applications/Claude.app\" --args --user-data-dir=\"$HOME/Library/Application Support/Claude-Work\" > /dev/null 2>&1 &"'`

```bash
open -n -a "/Applications/Claude.app" --args --user-data-dir="$HOME/Library/Application Support/Claude-<name>"
```
Manually launch the extra instance (same as the launcher). First run = log in, then quit.
Example: `open -n -a "/Applications/Claude.app" --args --user-data-dir="$HOME/Library/Application Support/Claude-Work"`

- Normal **Claude** app icon = your default account (untouched).
- New **Claude \<name\>** app = the extra account. First open may need: System Settings → Privacy & Security → **Open Anyway**.
- Drag it to the Dock. Done.

---

## CLI

```bash
cp -a ~/.claude ~/.claude-backup
```
Full backup of the current config.
Example: `cp -a ~/.claude ~/.claude-backup`

```bash
alias claude-default='CLAUDE_CONFIG_DIR="$HOME/.claude" claude'
```
Launch the CLI with the default config.
Example: `alias claude-personal='CLAUDE_CONFIG_DIR="$HOME/.claude" claude'`

```bash
alias claude-<name>='CLAUDE_CONFIG_DIR="$HOME/.claude-<name>" claude'
```
Launch the CLI with a separate config (first run = log in).
Example: `alias claude-work='CLAUDE_CONFIG_DIR="$HOME/.claude-work" claude'`

Add the aliases to `~/.zshrc`, then `source ~/.zshrc`.

---

## Notes

- Desktop and CLI use **different** config locations — they're independent.
  - Desktop: `~/Library/Application Support/Claude-<name>`
  - CLI: `~/.claude-<name>`
- Each config dir holds its own login, so you never re-login after the first time.
