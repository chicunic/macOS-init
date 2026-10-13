# GitHub

For a new Mac with keys already registered on GitHub. Install `gh` and `gpg-suite` via [Homebrew](homebrew.md) first.

## SSH Key

Restore your existing key pair, replacing `/path/to/backup` with your backup directory:

```bash
mkdir -p ~/.ssh
chmod 700 ~/.ssh
cp /path/to/backup/id_ed25519 /path/to/backup/id_ed25519.pub ~/.ssh/
chmod 600 ~/.ssh/id_ed25519
```

Add this block to `~/.ssh/config`; adjust the key filename if needed:

```sshconfig
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```

```bash
eval "$(ssh-agent -s)"
/usr/bin/ssh-add --apple-use-keychain ~/.ssh/id_ed25519
ssh -T git@github.com
```

For a key without a passphrase, omit `UseKeychain` and `--apple-use-keychain`. On first connection, verify GitHub's host fingerprint before accepting. Successful authentication exits with status `1`.

## GPG Key

Import your private-key backup and find its long key ID for `YOUR_KEY_ID` below:

```bash
gpg --import ~/gpg-private.asc
gpg --list-secret-keys --keyid-format=long
```

## Git Configuration

Replace the identity and `YOUR_KEY_ID`; use the same GitHub-verified email as your GPG key:

```bash
gh auth login --hostname github.com --git-protocol ssh --skip-ssh-key
gh auth status
git config --global user.name "your_name"
git config --global user.email "your_email@example.com"
git config --global gpg.format openpgp
git config --global user.signingkey YOUR_KEY_ID
git config --global commit.gpgsign true
git config --global init.defaultBranch main
```

## References

- [macOS SSH setup](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- [SSH connection test](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection)
- [SSH host fingerprints](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints)
- [Git signing configuration](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key)
- [GitHub CLI login](https://cli.github.com/manual/gh_auth_login)
