# macOS

## Dock

- Lock Dock position (left / bottom / right)

  ```bash
  defaults write com.apple.Dock position-immutable -bool true; killall Dock
  ```

- Set Dock icon size

  ```bash
  defaults write com.apple.Dock tilesize -int 44; killall Dock
  ```

- Lock Dock icon size

  ```bash
  defaults write com.apple.Dock size-immutable -bool true; killall Dock
  ```

## Screenshots

- Change screenshot filename prefix

  ```bash
  defaults write com.apple.screencapture name "Screenshot"
  ```

- Change screenshot save location

  ```bash
  mkdir -p ~/Pictures/Screenshots
  defaults write com.apple.screencapture location ~/Pictures/Screenshots
  ```

## Finder

- Show hidden files

  ```bash
  defaults write com.apple.finder AppleShowAllFiles -bool true; killall Finder
  ```

- Show path bar

  ```bash
  defaults write com.apple.finder ShowPathbar -bool true; killall Finder
  ```

- Show status bar

  ```bash
  defaults write com.apple.finder ShowStatusBar -bool true; killall Finder
  ```

- Show file extensions

  ```bash
  defaults write NSGlobalDomain AppleShowAllExtensions -bool true; killall Finder
  ```

- Use list view by default

  ```bash
  defaults write com.apple.finder FXPreferredViewStyle -string "Nlsv"; killall Finder
  ```

- Disable warning when changing file extensions

  ```bash
  defaults write com.apple.finder FXEnableExtensionChangeWarning -bool false; killall Finder
  ```

- Open new windows in home directory

  ```bash
  defaults write com.apple.finder NewWindowTarget -string "PfHm"; killall Finder
  ```

- Sort folders before files

  ```bash
  defaults write com.apple.finder _FXSortFoldersFirst -bool true; killall Finder
  ```

- Open folders in tabs instead of new windows

  ```bash
  defaults write com.apple.finder FinderSpawnTab -bool true; killall Finder
  ```

## Settings

- Accessibility -> Pointer Control -> Trackpad Options -> Use trackpad for dragging -> Three Finger Drag

- Spotlight -> Uncheck Help Apple Improve Search

- Spotlight -> Results from System -> Uncheck iPhone Apps

- Sound -> Uncheck Play sound on startup

- Privacy & Security -> Accessories -> Always ask
