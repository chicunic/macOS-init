# Homebrew

For Apple Silicon and zsh. Source builds require [Xcode or Command Line Tools](xcode.md).

## Install Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Run once to configure `~/.zprofile` and the current shell:

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv zsh)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv zsh)"
```

## Install Formulae

Common tools:

```bash
brew install autojump gh tree wget
```

Development tools:

```bash
brew install direnv node openjdk pipx uv
```

## Configure Development Tools

### pipx

Add pipx's application directory to `PATH`, then open a new terminal:

```bash
pipx ensurepath
```

### OpenJDK

Register the JDK with macOS:

```bash
sudo mkdir -p /Library/Java/JavaVirtualMachines
sudo ln -sfn "$(brew --prefix openjdk)/libexec/openjdk.jdk" /Library/Java/JavaVirtualMachines/openjdk.jdk
/usr/libexec/java_home -V
```

To prefer this JDK in `PATH`, add the following to `~/.zshrc`. The [bundled zshrc](../powerlevel10k/zshrc) already includes it:

```zsh
export PATH="/opt/homebrew/opt/openjdk/bin:$PATH"
```

For native builds that need the JDK headers, set this in the build shell:

```bash
export CPPFLAGS="-I/opt/homebrew/opt/openjdk/include"
```

## Install Casks

```bash
brew install --cask android-platform-tools appcleaner chatgpt claude claude-code coconutbattery docker-desktop google-chrome google-drive gpg-suite iina iterm2 keka onedrive stats typora@dev visual-studio-code realvnc-connect-viewer
```

## Upgrade Packages

Standard update check and upgrade:

```bash
brew update
brew outdated
brew upgrade
```

Set up and trust the third-party `buo/cask-upgrade` command:

```bash
brew trust --command buo/cask-upgrade/cu
brew tap buo/cask-upgrade
```

Review and upgrade casks, including apps with automatic updates:

```bash
brew cu -a
```

## Cleanup

Remove old formula versions, stale lock files, and outdated downloads:

```bash
brew cleanup
```

Include recent cached downloads; preview before running:

```bash
brew cleanup --dry-run -s --prune=all
brew cleanup -s --prune=all
```

## References

- [Homebrew installation](https://docs.brew.sh/Installation)
- [Homebrew commands](https://docs.brew.sh/Manpage)
- [Tap trust](https://docs.brew.sh/Tap-Trust)
- [pipx installation](https://pipx.pypa.io/latest/how-to/install-pipx.html)
- [OpenJDK](https://formulae.brew.sh/formula/openjdk)
- [Cask Upgrade](https://github.com/buo/homebrew-cask-upgrade)
