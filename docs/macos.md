# macOS

For macOS Golden Gate 27.

## Dock

- Lock the current Dock position:

  ```bash
  defaults write com.apple.Dock position-immutable -bool true; killall Dock
  ```

- Set Dock icon size to 44:

  ```bash
  defaults write com.apple.Dock tilesize -int 44; killall Dock
  ```

- Lock Dock icon size:

  ```bash
  defaults write com.apple.Dock size-immutable -bool true; killall Dock
  ```

## Screenshots

- Set screenshot filename prefix to `Screenshot`:

  ```bash
  defaults write com.apple.screencapture name "Screenshot"
  ```

- Save screenshots to `~/Pictures/Screenshots`:

  ```bash
  mkdir -p ~/Pictures/Screenshots
  defaults write com.apple.screencapture location ~/Pictures/Screenshots
  ```

  Or press `Shift+Command+5` -> `Options` -> `Save to` -> `Other Location…`.

## Finder

- Show hidden files:

  ```bash
  defaults write com.apple.finder AppleShowAllFiles -bool true; killall Finder
  ```

- Show path bar:

  ```bash
  defaults write com.apple.finder ShowPathbar -bool true; killall Finder
  ```

- Show status bar:

  ```bash
  defaults write com.apple.finder ShowStatusBar -bool true; killall Finder
  ```

- Show file extensions:

  ```bash
  defaults write NSGlobalDomain AppleShowAllExtensions -bool true; killall Finder
  ```

- Use list view by default (saved folder views take precedence):

  ```bash
  defaults write com.apple.finder FXPreferredViewStyle -string "Nlsv"; killall Finder
  ```

- Disable warnings when changing file extensions:

  ```bash
  defaults write com.apple.finder FXEnableExtensionChangeWarning -bool false; killall Finder
  ```

- Open new windows in the home directory:

  ```bash
  defaults write com.apple.finder NewWindowTarget -string "PfHm"; killall Finder
  ```

- Keep folders first when sorting by name:

  ```bash
  defaults write com.apple.finder _FXSortFoldersFirst -bool true; killall Finder
  ```

- Open folders in tabs with `Command` + double-click:

  ```bash
  defaults write com.apple.finder FinderSpawnTab -bool true; killall Finder
  ```

## Session Restore

Prevent macOS from saving the session's app list at logout, shutdown, or restart and relaunching those apps at the next login:

```bash
defaults write com.apple.loginwindow TALBlockSavingAndLaunch -bool true
```

Read the current override without changing it:

```bash
defaults read com.apple.loginwindow TALBlockSavingAndLaunch
```

`1` means blocking is enabled; `0` means it is disabled. A missing-key error means no explicit override is stored.

Delete the override to return control to macOS's normal session-restoration settings, including **Reopen windows when logging back in**:

```bash
defaults delete com.apple.loginwindow TALBlockSavingAndLaunch
```

If deletion reports that the key does not exist, the override is already absent. Apps configured as Login Items or through LaunchAgents have separate startup settings.

This is an internal `loginwindow` preference. Its save-state handling was checked in macOS 27.2, but restart behavior has not been tested.

## Settings

- **Accessibility -> Pointer Control -> Trackpad Options**: Check `Use trackpad for dragging`, select `Three Finger Drag`, click `OK`.

- **General -> AirDrop & Continuity**: Under `Widgets & iPhone Mirroring`, select your preferred device from `iPhone`.

- **Menu Bar -> Clock Options**: Select `Digital`; check `Show the day of the week` and `Display the time with seconds`.

- **Menu Bar -> Battery -> Battery Options**: Check `Show Percentage`.

- **Desktop & Dock**: Uncheck `Show suggested and recent apps in Dock`.

- **Spotlight**: Uncheck `Help Apple Improve Search` and `iPhone Apps`.

- **Sound**: Uncheck `Play sound on startup`.

- **Privacy & Security -> Accessories**: Set `Allow accessories to connect` to `Always ask` (Apple Silicon laptops).

## References

- [Screenshot options](https://support.apple.com/guide/mac-help/mh26782/mac)
- [Finder settings](https://support.apple.com/guide/mac-help/mchlp2803/mac)
- [Clock options](https://support.apple.com/guide/mac-help/mchlb3236e90/mac)
- [Battery percentage](https://support.apple.com/guide/mac-help/mchlp1115/mac)
- [Desktop & Dock](https://support.apple.com/guide/mac-help/mchlp1119/mac)
- [Three-finger drag](https://support.apple.com/102341)
- [Accessory permissions](https://support.apple.com/102282)
