# configr

Command-line interface for managing your system configuration. Works in unix-like operating systems with Bash.

The idea is simple: Config files can quickly add up, especially when you're epicly ricing your system. Often, people will add aliases to their `.profile` to make it faster to open their config files. `configr` is a tool to keep track of where your config files are located and open them quickly.

To add a config file, run `configr add <name> <path>`. This will register the file with a short name. It can be named anything you like.

To open a config file, run `configr open <name>`. This makes it fast to open config files without needing to remember and type out the full path, and without needing to populate your profile with aliases.

The list of registered config names and paths are stored in `~/.config/configr/configmap`, so you can easily move it to another system or commit it into your giga chad `dotfiles` repository for flexing even harder on [/r/unixporn](https://www.reddit.com/r/unixporn/).

## Installation

All you need is the `configr` file. Download it and put it somewhere in your PATH, like `/usr/bin/`. Make it executable with `chmod +x /path/to/configr`.

Here's an example:

```bash
git clone https://github.com/auderer/configr.git
sudo cp ./configr/configr /usr/bin/
sudo chmod +x /usr/bin/configr
```

## Configuration

Ironically, `configr` has no configuration as of now. The saved config map is stored in `~/.config/configr/configmap` by default. You can change this by setting `$CONFIGRCONFIG` to the file path you want to use. In this way, you could potentially have multiple separate sets of configs.

When opening a config file using `configr`, it will use the editor you define in the `EDITOR` environment variable.

```bash
export CONFIGRCONFIG=~/.config/configr/alternative-configmap
configr add foo bar
```

## Usage

```bash
# Show help information / command usage
configr help

# Register a new config file
configr add <name> </path/to/file>

# Print the location of a registered config
configr get <name>

# Change the location of a registered config
configr mv <name> </path/to/file>

# Remove a config file
configr rm <name>

# Open a registered config file in the default editor. Uses xdg-open.
configr open <name>

# Show all registered configs
configr list
```
