# dotfiles and terminal notes

This is a collection of my preferences so as to allow quick setup and continuity between machines I use for development

#### Go to and follow the instructions on the following link

[Beautiful Terminal Guide](https://medium.com/@shivam1/make-your-terminal-beautiful-and-fast-with-zsh-shell-and-powerlevel10k-6484461c6efb)

This will take you through setup of:

- Oh my zsh
- powerlevel10K

## Steps to bootstrap a new Mac

Source: [Beyond Dotfiles in 100 seconds](https://github.com/eieioxyz/Beyond-Dotfiles-in-100-Seconds/blob/master/README.md)

1. Install Apple's Command Line Tools, which are prerequisites for Git and Homebrew.

```zsh
xcode-select --install
```

2. Clone repo into new hidden directory.

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
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Then pass in the Brewfile location...
brew bundle --file ~/dotfiles-zsh/Brewfile

# ...or move to the directory first.
cd ~/dotfiles-zsh && brew bundle
```

## TODO List

- Learn how to use [`defaults`](https://macos-defaults.com/#%F0%9F%99%8B-what-s-a-defaults-command) to record and restore System Preferences and other macOS configurations.
- Automate symlinking and run script files with a bootstrapping tool like [Dotbot](https://github.com/anishathalye/dotbot).
- Revisit the list in [`.zshrc`](.zshrc) to customize the shell.
- Create a [bootable USB installer for macOS](https://support.apple.com/en-us/HT201372).
- Integrate other cloud services into your Dotfiles process (Dropbox, Google Drive, etc.).
- Find inspiration and examples in other Doffiles repositories at [dotfiles.github.io](https://dotfiles.github.io/).
