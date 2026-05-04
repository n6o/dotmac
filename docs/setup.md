# Setup

## MacOS configuration

### System updates and configuration

```bash
# Check for updates
softwareupdate -l

# Install updates
softwareupdate -i -a

# Disable startup chime
sudo nvram StartupMute=%01
```

### Dock configuration

```bash
# Set Dock icon size
defaults write com.apple.dock tilesize -int 64

# Set Dock minimize effect
defaults write com.apple.dock mineffect -string scale

# Disable Dock launch animation
defaults write com.apple.dock launchanim -bool false

# Enable Dock auto-hide
defaults write com.apple.dock autohide -bool true

# Remove Dock auto-hide delay
defaults write com.apple.dock autohide-delay -int 0

# Remove Dock auto-hide animation duration
killall Dock
```

### Finder configuration

```bash
# Show all file extensions
defaults write NSGlobalDomain AppleShowAllExtensions -bool true

# Show hidden files
defaults write com.apple.Finder AppleShowAllFiles -bool true

# Show path bar in Finder
defaults write com.apple.finder ShowPathbar -bool true
```

### Trackpad configuration

```bash
# Enable tap to click
defaults write com.apple.AppleMultitouchTrackpad  Clicking -bool true
```

### Install Xcode Command Line Tools

```bash
xcode-select --install
```

## Install prerequisites

### Install chezmoi

```bash
sh -c "$(curl -fsLS get.chezmoi.io)" -- -b $HOME/.local/bin
```

### Install mise

```bash
curl https://mise.run | sh
```

### Install Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## dotfiles installation

```bash
~/.local/bin/chezmoi init https://github.com/n6o/dotmac.git

~/.local/bin/chezmoi diff  

~/.local/bin/chezmoi apply -v
```

## zsh configuration

### completions

```bash
docker completion zsh > ~/.docker/completions/_docker
```
