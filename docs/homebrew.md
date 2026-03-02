# Homebrew

- Install Homebrew: [Official website](https://brew.sh/)

  ```bash
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  ```

- Set up environment variables

  ```bash
  echo >> ~/.zprofile
  echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
  eval "$(/opt/homebrew/bin/brew shellenv)"
  ```

- Install common formulae

  ```bash
  brew install autojump gh tree wget
  ```

- Install more dev tools

  ```bash
  brew install firebase-cli git-filter-repo golangci-lint gopls grpcurl node openjdk pipx protoc-gen-go protoc-gen-go-grpc staticcheck swag swiftformat swiftlint swiftly uv
  ```

- Check for formulae updates

  ```bash
  brew update
  brew outdated
  brew upgrade
  ```

- Enable cask update checking: [buo/cask-upgrade](https://github.com/buo/homebrew-cask-upgrade)

  ```bash
  brew tap buo/cask-upgrade
  ```

- Check for cask updates

  ```bash
  brew cu -a
  ```

- Install common casks

  ```bash
  brew install --cask aldente android-platform-tools antigravity appcleaner chatgpt claude claude-code coconutbattery copilot-cli docker-desktop figma google-chrome google-drive gpg-suite iina iterm2 keka notion onedrive stats typora@dev visual-studio-code vnc-viewer zoom
  ```

- Clean up Homebrew cache

  ```bash
  brew cleanup
  brew cleanup -s --prune=all
  ```
