# dotfiles and terminal notes

This is a collection of my preferences so as to allow quick setup and continuity between machines I use for development

## Steps to bootstrap a new Mac

psssst: you may be able to install oh-my-zsh with fig:
[Check out Fig!](https://fig.io/)

1. Install Apple's Command Line Tools, which are prerequisites for Git and Homebrew. On newer macs this comes out of the box

```zsh
xcode-select --install
```

2. Clone repo into new directory.

```zsh
# Use SSH (if set up)...
git clone git@github.com:aukoyy/dotfiles-zsh.git ~/.
```

3. Create symlinks in the Home directory to the real files in the repo.

```zsh
# There are better and less manual ways to do this;
# investigate install scripts and bootstrapping tools.

ln -s ~/dotfiles-zsh/.zshrc ~/.zshrc
ln -s ~/dotfiles-zsh/.gitconfig ~/.gitconfig
```

4. Install Homebrew, followed by the software listed in the Brewfile.

```zsh
# These could also be in an install script.

# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

# Then pass in the Brewfile if you would like to install these programs.
brew bundle --file ~/dotfiles-zsh/Brewfile

******** DONT RUN FOR INSTALL: ********
# IF you want to remove homebrew, run the uninstall script, followed by the provided removebrew.sh script

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall.sh)"

sh removebrew.sh

********
```

5. Install oh-my-zsh
   ```zsh
   # Install oh-my-zsh
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
    # Install PowerLevel10K
    git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
    # Configure PowerLevel10K
    p10k configure
   ```
   [Beautiful Terminal Guide](https://medium.com/@shivam1/make-your-terminal-beautiful-and-fast-with-zsh-shell-and-powerlevel10k-6484461c6efb)

## TODO List

- Learn how to use [`defaults`](https://macos-defaults.com/#%F0%9F%99%8B-what-s-a-defaults-command) to record and restore System Preferences and other macOS configurations.
- Automate symlinking and run script files with a bootstrapping tool like [Dotbot](https://github.com/anishathalye/dotbot).
- Find inspiration and examples in other Doffiles repositories at [dotfiles.github.io](https://dotfiles.github.io/).

### Sources

Source: [Beyond Dotfiles in 100 seconds](https://github.com/eieioxyz/Beyond-Dotfiles-in-100-Seconds/blob/master/README.md)
