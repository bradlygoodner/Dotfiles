# Super-Engine
## Steps to bootstrap a new Mac
1. Install Apple's Command Line Tools, which are prerequisites for Git and Homebrew.
```bash
    xcode-select --install
```
2. Clone repo into new hidden directory.
```bash
# Use SSH (if set up)...
  git clone git@github.com:bradlygoodner/super-engine.git ~/.dotfiles

#...or use HTTPS and switch remotes later.
  git clone https://github.com/bradlygoodner/super-engine.git ~/.dotfiles
```
3. Creat symlinks in the Home directory to the real files in the repo.
```bash
  # There are better and less manual ways to do this;
  # Investigate install scripts and bootstrapping tools.

  ln -s ~/.dotfiles/.zshrc ~/.zshrc
  ln -s ~/.dotfiles/.gitconfig ~/.gitconfig
```
4. Install Homebrew, followed by the software listed in the Brewfile.
```bash
  # These could also be in an install script.

  # Install Homebrew

  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

  # Then pass in the Brewfile location...
  brew bundle --file ~/.dotfiles/Brewfile

  #...or move to the directory first.
  cd ~/.dotfiles && brew bundle
```

Check out 
- [dotfiles.github.com](dotfiles.github.com)
- [dotfiles.eieio.xyz](dotfiles.eieio.xyz)