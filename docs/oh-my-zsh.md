# Oh My Zsh

## Install Oh My Zsh

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Plugins

```bash
brew install autojump direnv
```

In `~/.zshrc`, set this before `source "$ZSH/oh-my-zsh.sh"`:

```zsh
plugins=(autojump direnv git)
```

## Powerlevel10k

```bash
brew install --cask font-meslo-for-powerlevel10k
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git "${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k"
```

Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`.

## Quick Setup

From the repository root, restore the bundled [zshrc](../powerlevel10k/zshrc) and [p10k.zsh](../powerlevel10k/p10k.zsh):

```bash
cp powerlevel10k/zshrc ~/.zshrc
cp powerlevel10k/p10k.zsh ~/.p10k.zsh
exec zsh
```

Optional: run `p10k configure` to change the prompt style.

## References

- [Oh My Zsh installation](https://ohmyz.sh/#install)
- [Oh My Zsh plugins](https://github.com/ohmyzsh/ohmyzsh#enabling-plugins)
- [Powerlevel10k installation](https://github.com/romkatv/powerlevel10k#oh-my-zsh)
- [Powerlevel10k fonts](https://github.com/romkatv/powerlevel10k#fonts)
