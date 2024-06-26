<p align="center">
  <img
    src="./assets/banner.png"
    alt="dotfiles"
    style="width:100%;"
  />
</p>

## Configure NVIM Config

Go to the repo directory and use symlink for nvim config

```sh
ln -s $(pwd)/.config/nvim ~/.config
ln -s $(pwd)/.config/terminalizer ~/.config
```

## Setup Homebrew

Install homebrew as Package Manager for mac to able to use brew command, check the documentation [here](https://brew.sh/)

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

After installing Homebrew, do

```sh
brew bundle --file=/Brewfile
```

## Configure Zed

Copy settings from zed [settings](.config/zed/settings.json) to .config/zed/settings.json

Or, using symlink to link directly the folder to your config

```sh
ln -s $(pwd)/.config/zed ~/.config
```

## Configure VSCode

Install VSCode from [here](https://code.visualstudio.com/) or using brew command for mac

```sh
brew install --cask visual-studio-code
```

Copy settings from vscode [settings](.config/vscode/settings.json) to VSCode Settings

Install all extensions that we needed with this command

```sh
cat .config/vscode/extensions.list | xargs -L 1 code --install-extension
```

## Setup TMUX

### Relevant Files

- [.tmux.conf](.tmux.conf)

Install TMUX with Homebrew:

```sh
brew install tmux
```

Install Tpm (TMUX Package Manager):

```sh
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

Install all plugins in TMUX with command: `Ctrl-a + Shift-i`

## Setup Neovim

### Relevant Files

- [.config/nvim](.config/nvim)

### Setup Requires

- True Color Terminal Like: [iTerm2](https://iterm2.com/)
- [Neovim](https://neovim.io/) (Version 0.9 or Later)
- [Nerd Font](https://www.nerdfonts.com/) - I use Meslo Nerd Font
- [Ripgrep](https://github.com/BurntSushi/ripgrep) - For Telescope Fuzzy Finder
- XCode Command Line Tools

Install Deps with Homebrew:

```sh
brew install --cask iterm2

brew install node vim neovim tree-sitter git fd ripgrep lazygit lua luajit
```

For XCode Command Line Tools do:

```bash
xcode-select --install
```

Optional deps

```sh
brew install lsd eza tree
```

If you have already installed vim, create a symbolic link to map directly neovim with vim

```sh
ln -s $(which nvim) /opt/homebrew/bin/vim
```

## Setup Terminalizer

Install Terminalizer from NPM

```sh
npm install -g terminalizer
```

### Setup Go on Neovim

Install binaries on running this command `GoInstallBinaries`

## Uninstall nvim

```sh
# Linux / Macos (unix)
rm -rf ~/.config/nvim
rm -rf ~/.local/share/nvim

# Windows
rd -r ~\AppData\Local\nvim
rd -r ~\AppData\Local\nvim-data
```

## License

[MIT](LICENSE)
