# Nimbus releases

Installers and automatic updates for **Nimbus**, a desktop weather companion. The app's source lives in a private repository; this repository only builds and publishes its releases.

## Download

Open the [latest release](https://github.com/hillaryozoma/nimbus-releases/releases/latest) and pick the file for your system:

- **Windows:** `Nimbus_<version>_x64-setup.exe` (installs for your account, no admin rights needed) or `Nimbus_<version>_x64_en-US.msi`
- **macOS:** `Nimbus_<version>_aarch64.dmg` (Apple silicon) or `Nimbus_<version>_x64.dmg` (Intel)
- **Linux:** `.AppImage`, `.deb` or `.rpm`

Installed copies update themselves from this repository.

## How releases are built

`.github/workflows/release.yml` checks out the private source with a read-only deploy key, builds every platform, signs the updater artifacts, and creates a **draft** release with the installers and `latest.json`. Run it from the Actions tab, or with:

```bash
gh workflow run release.yml -R hillaryozoma/nimbus-releases -f ref=<tag or branch>
```

Publishing the draft makes it the update that installed copies download.

Weather data by [Open-Meteo.com](https://open-meteo.com) (CC BY 4.0).
