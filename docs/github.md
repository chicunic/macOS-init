# GitHub

## SSH Key

- Generate SSH key

  ```bash
  ssh-keygen -t ed25519 -C "your_email@example.com"
  ```

- Add to ssh-agent

  ```bash
  eval "$(ssh-agent -s)"
  ssh-add ~/.ssh/id_ed25519
  ```

- Add to GitHub: [Settings -> SSH and GPG keys](https://github.com/settings/keys)

- Test connection

  ```bash
  ssh -T git@github.com
  ```

## GPG Key

- Generate GPG key

  ```bash
  gpg --full-generate-key
  ```

- List GPG keys

  ```bash
  gpg --list-secret-keys --keyid-format=long
  ```

- Export GPG key

  ```bash
  gpg --export-secret-keys --armor your_email@example.com > gpg-private.asc
  ```

- Import GPG key

  ```bash
  gpg --import gpg-private.asc
  ```

- Set trust level

  ```bash
  echo -e "5\ny\n" | gpg --command-fd 0 --expert --edit-key your_email@example.com trust quit
  ```

- Add to GitHub: [Settings -> SSH and GPG keys](https://github.com/settings/keys)

## Git Config

```bash
gh auth login
git config --global user.name "your_name"
git config --global user.email "your_email@example.com"
git config --global user.signingkey 0123456789ABCDEF
git config --global commit.gpgsign true
git config --global init.defaultBranch main
```
