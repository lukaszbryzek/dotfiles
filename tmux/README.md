# tmux

Full tmux config in one minute.

## Installation

### Prerequisites

- **tmux** -- duh?
- **Rust + Cargo** -- to compile for Apple Silicon, otherwise you can most likely skip
- **fzf** -- [Fuzzy Finder](https://github.com/junegunn/fzf)
- **Minimum 256-color teminal** -- 16 would work too but it's gonna be ugly
- **stow** -- You can play manually but if you're lazy like me then GNU Stow is your friend.
- **Git** -- How you're gonna clone this repo, eh?

### Installation

Having all prerequisites ready you're just a couple of commands away from getting my tmux setup.

#### dotfiles philosophy

Before we begin, decide where your dotfiles reside? My general idea is that:

1. You clone this repo to `~/.dotfiles` as a local storage for all of the config files.
2. You put all of the config files for all programs under `~/.config` to have a clean Home Directory.

This way you get something like this:

```bash
$ tree .config
.config
├── tmux -> ../.dotfiles/tmux/tmux
└── mc
    ├── ini
    ├── mcedit
    └── panels.ini
```

Clean Home Directory and everything under .config pointing at .dotfiles

Having said that - let's begin:

```bash
# Clone this repo to ~/.dotfiles directory.
git clone https://github.com/lukaszbryzek/dotfiles.git ~/.dotfiles

# Enter the directory.
cd ~/.dotfiles

# See what sow is going to do using dry-run `-n`.
stow -n -v tmux
# The output should be like:
# LINK: tmux => ../.dotfiles/tmux/tmux
# WARNING: in simulation mode so not modifying filesystem.

# Install the tmux config files (in verbose mode just because we can).
stow -v tmux

# Clone TPM (Tmux Plugin Manager) - required for tmux.
# Plugins are stored in ~/.local/share/tmux/plugins (XDG_DATA_HOME)
git clone https://github.com/tmux-plugins/tpm ~/.local/share/tmux/plugins/tpm

# Start tmux.
tmux
```

And voila! Tmux is runnng! Just one thing to do after first run...

## First Run

When you run your tmux for the first time it's gonna be ugly. That's because you only have:

- key bindings
- some interface customisations (like status bar on top)
- TPM installed

And the last part is the greatest! My config uses CTRL+a as tmux prefix so now press these two key combos:

1. Ctrl+A
2. Shift+I

Yup, two key strokes. First Control and "A", release them, then Shift and "I". Relase them. And wait.
