# PoE 2 Smoother

Windows tool for applying modular Path of Exile 2 client file patches.

The app does **not** inject into the game process, hook memory, or attempt to bypass anti-cheat. It modifies client files only through the configured game file store and creates immutable backups before the first write.

## Warning

Modifying Path of Exile 2 client files may violate the game's terms of service and can risk account or file integrity issues. Use at your own risk and keep a clean restore path available.

## Download

Download the latest release from [GitHub Releases](https://github.com/MoonFlowen/PoE2Smoother/releases).

Extract the **entire ZIP** to any folder and run `PoE2Smoother.App.exe`. No .NET runtime installation is required.

## Updating to a new version

The app does not auto-update. To install a newer release:

1. Close PoE 2 Smoother.
2. Download the latest `PoE2Smoother-<version>-win-x64.zip` from [Releases](https://github.com/MoonFlowen/PoE2Smoother/releases).
3. Extract the full archive into your existing install folder (overwrite files) or into a new folder.
4. Run `PoE2Smoother.App.exe`.

Your settings, backups, and license are stored in `%AppData%\PoE2Smoother\` and are kept when you replace the install folder. Keep all files from the ZIP together — do not copy only the exe.

After a PoE 2 game patch, use the **Re-patch** banner or **Quick Optimize** even if the app version did not change.

## Requirements

- Windows x64
- Path of Exile 2 (Steam or standalone)

The release already includes `oo2core_9_win64.dll`, which is required to read PoE 2 game bundles. Keep it in the same folder as `PoE2Smoother.App.exe`.

## Quick start

1. Download and extract the latest release ZIP **with all files in one folder**.
2. Start `PoE2Smoother.App.exe` — the app auto-detects PoE 2 if installed via Steam or standalone.
3. Activate a license key (License button).
4. Click **Quick Optimize** to apply map reveal, remove soft particles, set zoom to 1.8x, and patch in one step.
5. After a game patch, use the **Re-patch** banner or Quick Optimize again.
6. Use **Restore** to revert all patched files to their original snapshots.

## License activation

Patch, Verify, and Quick Optimize require an active license.

1. Click **License** in the app.
2. Enter your license key and click **Activate**.
3. After activation, patch operations are unlocked until the license expires.

If the license server is temporarily unavailable, the app may continue in offline grace mode for up to 72 hours using the last validated license.

## Advanced workflow

1. Configure options in the Map / Visual / Sounds / Performance tabs.
2. Click **Verify** to preview planned changes.
3. Click **Patch** to apply.
4. Use **Restore** to revert all changes.

On first run, the app creates:

- `%AppData%\PoE2Smoother\settings.json`
- `%AppData%\PoE2Smoother\backups`

## Features

### Map
- Readable map layout with configurable outline colors
- Atlas fog removal

### Visual
- Camera zoom (adjustable multiplier)
- Fog, rain, clouds, environment particles
- Shadows, lights, delirium, particles, effects
- Screen shake removal, corpse removal
- Soft particles, darkness reduction, better lights
- **Keep important effects** — preserves boss telegraphs and league markers

### Sounds
- Disable ambient sounds
- Silent skills and monsters

### Performance
- Soft / full MTX particle removal
- Fast hideout / Black screen (experimental) — scans login/character-selection and hideout dependencies (including Dreadnought) before patching
- Character, per-monster, terrain decoration, stash, and `.epk` packages are left untouched by black-screen mode

### UX
- **Quick Optimize** — one-click map reveal, soft particles removal, and 1.8x camera zoom + patch
- Analyze (Verify) with diff preview before patching
- Re-patch banner after game updates
- Backup status and one-click Restore All

## Package contents

| File | Description |
|------|-------------|
| `PoE2Smoother.App.exe` | Main application |
| `oo2core_9_win64.dll` | Bundled Oodle library for reading PoE 2 bundles |
| `*.dll` | Required WPF runtime libraries — keep them next to the exe |
| `README.md` | This guide |
| `OODLE.txt` | Short note about the bundled Oodle library |

**Important:** do not move `PoE2Smoother.App.exe` without the other DLL files from the archive.

## Troubleshooting

### Oodle / Verify errors

The release already includes `oo2core_9_win64.dll`. If Verify still fails with an Oodle error:

1. Make sure you extracted the full ZIP, not only the exe.
2. Keep `oo2core_9_win64.dll` in the same folder as `PoE2Smoother.App.exe`.
3. After a major PoE 2 update, replace `oo2core_9_win64.dll` with the copy from your PoE 2 game folder if needed.

### Game updated / patches stopped working

When Path of Exile 2 patches, client files change. The app shows a **Re-patch** banner when it detects a client fingerprint mismatch. Click **Re-patch** or **Quick Optimize** to re-apply your profile.

### Verify Game Files

Steam or standalone file verification restores original game files and removes applied patches. Use **Restore** in the app first, or re-patch after verification.

### License issues

- **License expired** — click **License** and activate a new key.
- **Offline grace** — reconnect to the internet and restart the app to re-validate.
