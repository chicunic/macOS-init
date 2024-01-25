# macOS-init

适用于 macOS 的初始化脚本，用于安装常用软件和配置系统。

## LaunchPad

- 还原 LaunchPad 图标布局

  ```bash
  defaults write com.apple.dock ResetLaunchPad -bool yes; killall Dock
  ```

- 锁定 Dock 栏位置（左边 / 底部 / 右边）

  ```bash
  defaults write com.apple.Dock position-immutable -bool yes; killall Dock
  ```

- 锁定 Dock 栏高度

  ```bash
  defaults write com.apple.Dock size-immutable -bool yes; killall Dock
  ```

- 锁定 Dock 栏图标内容

  ```bash
  defaults write com.apple.Dock contents-immutable -bool yes; killall Dock
  ```

## Xcode

- 安装 Xcode

  - 通过 AppStore 安装（推荐） [Xcode](https://apps.apple.com/us/app/xcode/id497799835?l=zh-Hans-CN&mt=12)

  - [官方网站](https://developer.apple.com/cn/xcode/)

- 安装 Xcode Command Line Tools

  ```bash
  xcode-select --install
  ```

## oh-my-zsh

- 安装 oh-my-zsh [官方网站](https://ohmyz.sh/#install)

  ```bash
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```

## Homebrew

- 安装 Homebrew [官方网站](https://brew.sh/zh-cn/)

  ```bash
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  ```

- 安装常用的 formulae

  ```bash
  brew install autojump gh git openssh zsh
  ```

- 检查 formulae 更新

  ```bash
  brew update
  brew outdated
  brew upgrade
  ```

- 启用 cask 更新检查

  ```bash
  brew tap buo/cask-upgrade
  ```

- 检查 cask 更新

    ```bash
    brew cu -a
    ```

- 安装常用的 cask

  ```bash
  brew install adobe-acrobat-reader appcleaner cloudflare-warp google-chrome iina iterm2 keka kekaexternalhelper onedrive
  ```

- 清理 Homebrew 缓存

  ```bash
  brew cleanup
  brew cleanup -s --prune=all
  ```
