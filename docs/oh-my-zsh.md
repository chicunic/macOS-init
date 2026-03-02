# oh-my-zsh

- Install oh-my-zsh: [Official website](https://ohmyz.sh/#install)

  ```bash
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```

- Reference config: [robbyrussell/zshrc](../robbyrussell/zshrc)

- Install plugins

  ```bash
  # autojump (included in Homebrew formulae)
  # git (built-in with oh-my-zsh)
  ```

  Set `plugins=(autojump git)` in `~/.zshrc`.

## powerlevel10k

- [Official website](https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#oh-my-zsh)

- Install fonts

  ```bash
  brew install font-meslo-for-powerlevel10k
  ```

- Install via oh-my-zsh (recommended)

  ```bash
  git clone --depth=1 https://github.com/romkatv/powerlevel10k.git "${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k"
  ```

  Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`.

- Initialize

  ```bash
  p10k configure
  ```

- Reference configs: [powerlevel10k/zshrc](../powerlevel10k/zshrc), [powerlevel10k/p10k.zsh](../powerlevel10k/p10k.zsh)
