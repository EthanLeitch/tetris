# tetris [![Build Status](https://travis-ci.org/samtay/tetris.svg?branch=master)](https://travis-ci.org/samtay/tetris)

A terminal interface for Tetris

![terminal-gif](./docs/img/play.gif)

## installation
Installation on MacOS and Linux is outlined below. Windows support is questionable, but you can try to install from [source](#install-from-source) or via [dex](#install-via-dex).

#### MacOS
Installation on a Mac is simple with Homebrew:
```bash
brew install samtay/tui/tetris
```
#### Arch Linux
Arch Linux users can install from the [AUR](https://aur.archlinux.org/packages/tetris-terminal-git/), e.g.
```bash
yay -S tetris-terminal-git # or yaourt, etc.
```
#### Snapcraft
Thanks to **@thefenriswolf** this is available on most Linux distributions via [snapcraft](https://snapcraft.io/tetris-thefenriswolf):
```bash
sudo snap install tetris-thefenriswolf
```
#### install from source
First [get stack](https://docs.haskellstack.org/en/stable/README/#how-to-install). Then
```bash
git clone https://github.com/samtay/tetris.git
cd tetris
stack install tetris
```

#### install via dex
[dex](https://github.com/dockerland/dex) is a really cool application manager that lets you run executables as docker images, so that you don't need to worry about installing them or their dependencies directly.
```bash
# get dex if you don't have it
curl -L http://get.iceburg.net/dex/latest-0.12.x/dex -o dex
chmod +x dex
sudo mv dex /usr/local/bin

# add tetris as a repo
dex repo add tetris https://github.com/samtay/tetris.git

# run tetris
dex run tetris

### optionally install tetris globally ###
export PATH="$HOME/.dex/bin:$PATH"
dex install --global tetris
tetris
```

## usage

The default game is run by simply executing the `tetris` command.
If the unicode characters look a bit
wonky in your terminal, you can also run
```shell
tetris --ascii-only         # uses [] as preview cell
# or
tetris --preview-chars 'XX' # uses custom characters as preview cell
```
If you want to skip the level prompt, you can start the game immediately via
```shell
tetris --level n
```
Lastly, to see the current high score, you can run `tetris --high-score`.
And of course, see `tetris --help` for help.

## tips

#### troubleshooting
People seem to have varying levels of success with the linux binary. Please note that it is compiled dynamically and hence should not be expected to work on most distros. If you have other problems, feel free to open an issue.

#### roll your own
If you like games in your terminal and have an interest in functional programming, write your own! This code is built on top of [brick](https://github.com/jtdaugherty/brick) which makes building terminal user interfaces very accessible. I also have a [tutorial](https://samtay.github.io/posts/introduction-to-brick) that can help you get started.
