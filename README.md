# configr

Command-line interface for quickly editing your system configuration.

Works in unix-like operating systems with Bash.

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