# Xcode

## Xcode App

- [App Store](https://apps.apple.com/app/xcode/id497799835)
- [Specific or beta versions](https://developer.apple.com/download/all/)

Open Xcode and complete setup, then select its tools:

```bash
sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
```

Or **Xcode -> Settings -> Locations**: Select the installed version under `Command Line Tools`.

Verify:

```bash
xcode-select -p
xcodebuild -version
```

## Standalone Command Line Tools

Install if you don't need the full Xcode app:

```bash
xcode-select --install
```

Select the installed standalone tools:

```bash
sudo xcode-select --switch /Library/Developer/CommandLineTools
```

## References

- [Command Line Tools settings](https://developer.apple.com/documentation/xcode/configuring-command-line-tools-settings)
