# iTerm2

For iTerm2 3.7.4. Open **iTerm2 -> Settings…** (`Command+,`).

## Sync Settings

Under **General -> Settings**:

1. Check `Load settings from a custom folder or URL`.
2. Select the `iterm2` folder in iCloud Drive:

   ```text
   ~/Library/Mobile Documents/com~apple~CloudDocs/iterm2
   ```

3. Set `Save changes` to `Automatically`.

Settings file: `com.googlecode.iterm2.plist`.

## Manual Configuration

### General

- **General -> Closing**: Check `Quit when all windows are closed`.
- **General -> Software Update -> Shell Integration Updates**: Check `Ignore non-critical shell integration updates`.
- **General -> Selection -> Command selection**: Uncheck `Clicking on a command selects it to restrict Find and Filter`.
- **General -> Window**: Set `New window placement` to `Remember the position of previously closed windows and use size from profile`.

Window size comes from `Columns` and `Rows` under **Profiles -> Window**.

### AI (Optional)

Under **General -> AI -> General**:

1. Install the `AI Plugin` if needed.
2. Under `Consent`, check `Enable generative AI features`.
3. Select `Gemini` and a model under `AI Model`; enter your Gemini API key.
4. Use `Manage AI Models` for custom models. Check `Automatically update available AI models from live online database` to update the model list.

API keys are stored in Keychain; configure them on each Mac.

### Profiles

Under **Profiles**, select `Default`:

- **Colors -> Modes**: Uncheck `Use separate colors for light and dark mode`.
- **Colors**: Set `Color Presets…` to `Dark Background`.
- **Text**: Set `Font` to `MesloLGS NF`, `Regular`, size `12`.
- **Session -> Closing**: Set `Prompt before closing?` to `Never`.

Install [Meslo for Powerlevel10k](fonts.md#meslo-for-powerlevel10k) before selecting the font.

## References

- [General settings](https://iterm2.com/documentation-preferences-general.html)
- [Profile colors](https://iterm2.com/documentation-preferences-profiles-colors.html)
- [Profile text](https://iterm2.com/documentation-preferences-profiles-text.html)
- [Profile session](https://iterm2.com/documentation-preferences-profiles-session.html)
- [AI Plugin](https://iterm2.com/ai-plugin.html)
