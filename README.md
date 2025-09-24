# macOS-init

适用于 macOS 的初始化脚本，用于安装常用软件和配置系统。

## LaunchPad

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

## Screenshots

- 修改截图文件名前缀

  ```bash
  defaults write com.apple.screencapture name "Screenshot"
  ```

- 修改截图文件保存路径

  ```bash
  mkdir -p ~/Pictures/Screenshots
  defaults write com.apple.screencapture location ~/Pictures/Screenshots
  ```

## Xcode

- 安装 Xcode

  - 通过 AppStore 安装 (推荐) [Xcode](https://apps.apple.com/us/app/xcode/id497799835?l=zh-Hans-CN&mt=12)

  - 下载安装包 (不推荐) [官方网站](https://developer.apple.com/cn/xcode/)

- 安装 Xcode Command Line Tools

  ```bash
  xcode-select --install
  ```

- 查看 Xcode Command Line Tools 路径

  ```bash
  xcode-select -p
  ```

## Settings

- Spotlight -> 取消选中 Help Apple Improve Search

- Spotlight -> Results from System -> 取消选中 iPhone Apps

- Sound -> 取消选中 Play sound on startup

- Privacy & Security -> Accessories -> Always ask

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

- 配置环境变量

  ```bash
  echo >> ~/.zprofile
  echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
  eval "$(/opt/homebrew/bin/brew shellenv)"
  ```

- 安装常用的 formulae

  ```bash
  brew install autojump gh go node tree wget
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
  brew install google-chrome
  ```

- 其他推荐的 cask

  ```bash
  adobe-acrobat-reader
  aldente
  android-platform-tools
  appcleaner
  chatgpt
  claude
  coconutbattery
  font-inconsolata
  font-meslo-for-powerlevel10k
  font-roboto
  google-chrome
  google-drive
  gpg-suite
  iina
  iterm2
  keka
  kekaexternalhelper
  notion
  onedrive
  stats
  typora@dev
  visual-studio-code
  vnc-viewer
  ```

- 清理 Homebrew 缓存

  ```bash
  brew cleanup
  brew cleanup -s --prune=all
  ```

## iTerm2

- 配置关闭所有窗口时退出 iTerm2

  Settings -> General -> Closing, 选中 Quit when all windows are closed

- 禁用鼠标点击选中命令

  Settings -> General -> Selection, 取消选中 Click on a command selects it to restrict Find and Filter

- 禁用记住尺寸和位置

  Settings -> General -> Window, 取消选中 Remember the size and position of previously closed windows

- 修改主题颜色为黑色

  Settings -> Profiles -> Colors, 取消选中 Use separate colors for light and dark mode, Color Presets 选择 Dark Background

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
  git config --global init.defaultBranch main
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
  git clone --depth=1 https://github.com/romkatv/powerlevel10k.git "${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k"
  ```

  Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`.

- 初始化

  ```bash
  p10k configure
  ```
