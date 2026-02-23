# TideArch Packages

## 1 shell

### 1.1 bash

bash comes installed with archlinux by default

### 1.2 brush

using pacman:

    sudo pacman -S brush

### 1.3 zsh

using pacman:

    sudo pacman -S zsh

recommended to use with oh-my-zsh:

    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

also recommended to use with powerlevel10k:

    git clone --depth=1 https://github.com/romkatv/powerlevel10k.git "${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k"

edit the zsh theme in the configuration file:

    text-editor ~/.zshrc

change `ZSH_THEME` value to `"powerlevel10k/powerlevel10k"`.

### 1.4 fish

using pacman:

    sudo pacman -S fish

## 2 terminal
