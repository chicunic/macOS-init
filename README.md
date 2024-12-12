# macOS-init

适用于 macOS 的初始化脚本，用于安装常用软件和配置系统。

## LaunchPad

- 还原 LaunchPad 图标布局

  ```bash
  defaults write com.apple.dock ResetLaunchPad -bool true; killall Dock
  ```

- 锁定 Dock 栏位置 (左边 / 底部 / 右边)

  ```bash
  defaults write com.apple.Dock position-immutable -bool true; killall Dock
  ```

- 设置 Dock 栏高度

  ```bash
  defaults write com.apple.Dock tilesize -int 44; killall Dock
  ```

- 锁定 Dock 栏高度

  ```bash
  defaults write com.apple.Dock size-immutable -bool true; killall Dock
  ```

- 锁定 Dock 栏图标内容

  ```bash
  defaults write com.apple.Dock contents-immutable -bool true; killall Dock
  ```

## Screenshots

- 修改截图文件名前缀

  ```bash
  defaults write com.apple.screencapture name "Screenshot"
  ```

- 修改截图文件保存路径

  ```bash
  defaults write com.apple.screencapture location ~/Pictures/Screenshots
  ```

## Xcode

- 安装 Xcode

  - 通过 AppStore 安装(推荐) [Xcode](https://apps.apple.com/us/app/xcode/id497799835?l=zh-Hans-CN&mt=12)

  - 下载安装包(不推荐) [官方网站](https://developer.apple.com/cn/xcode/)

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
  brew install adobe-acrobat-reader appcleaner cloudflare-warp google-chrome iina iterm2 keka kekaexternalhelper
  ```

- 清理 Homebrew 缓存

  ```bash
  brew cleanup
  brew cleanup -s --prune=all
  ```

## iTerm2

- 配置关闭所有窗口时退出 iTerm2

  iTerm2 -> Preferences -> General -> Closing, 选中 Quit when all windows are closed

- 禁用鼠标点击选中命令

  iTerm2 -> General -> Selection, 取消选中 Click on a command selects it to restrict Find and Filter

- 修改主题颜色为黑色

  iTerm2 -> Preferences -> Profiles -> Colors, 选中 Use different colors for light mode and dark mode, 选择 Dark Mode, 然后取消选中 Use different colors for light mode and dark mode

## GitHub

- 配置 SSH Key

  ```bash
  ssh-keygen -t ed25519 -C "your_email@example.com"
  ```

  列出 GPG Key

  ```bash
  gpg --list-secret-keys --keyid-format=long
  ```

- 配置 GitHub 账号

  ```bash
  gh auth login
  git config --global user.name "your_name"
  git config --global user.email "your_email@example.com"
  git config --global user.signingkey 0123456789ABCDEF
  git config --global commit.gpgsign true
  ```

## 安装常用字体

- Source Han Sans 思源黑体 [官方网站](https://github.com/adobe-fonts/source-han-sans/releases)

  下载 Static Super OTC 解压后双击安装

- Source Han Serif 思源宋体 [官方网站](https://github.com/adobe-fonts/source-han-serif/releases)

  下载 Static Super OTC 解压后双击安装

- Inconsolata, Roboto

  ```bash
  brew install font-inconsolata font-roboto
  ```

## powerlevel10k

- [官方网站](https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#oh-my-zsh)

- 安装字体

  ```bash
  brew install font-meslo-for-powerlevel10k
  ```

- 通过 oh-my-zsh 安装(推荐)

  ```bash
  git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
  ```

  Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`.

- 初始化

  ```bash
  p10k configure
  ```
