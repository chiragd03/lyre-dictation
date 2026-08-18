# Lyre update channel

This folder is served raw from the public GitHub repo `chiragd03/lyre-dictation`
and is what the app polls to discover new versions.

The app's updater endpoint (in `src-tauri/tauri.conf.json`) is:

    https://raw.githubusercontent.com/chiragd03/lyre-dictation/main/updates/latest.json

## `latest.json` (generated — do not hand-edit signatures)

Standard Tauri updater manifest. Produced by `packaging/make-update-manifest.sh`
after a signed build. Shape:

```json
{
  "version": "0.2.0",
  "notes": "Lyre 0.2.0.",
  "pub_date": "2026-01-01T00:00:00Z",
  "platforms": {
    "darwin-aarch64": {
      "signature": "<contents of Lyre_aarch64.app.tar.gz.sig>",
      "url": "https://github.com/chiragd03/lyre-dictation/releases/download/v0.2.0/Lyre_aarch64.app.tar.gz"
    },
    "darwin-x86_64": {
      "signature": "<contents of Lyre_x86_64.app.tar.gz.sig>",
      "url": "https://github.com/chiragd03/lyre-dictation/releases/download/v0.2.0/Lyre_x86_64.app.tar.gz"
    }
  }
}
```

`windows-x86_64` is added later once the Windows updater path is wired (see the
stub notes in `packaging/build-windows.ps1`).

## Release flow

1. `bash packaging/bump-version.sh 0.2.0`
2. On an Apple Silicon Mac: `bash packaging/build-mac.sh` then
   `bash packaging/make-update-manifest.sh 0.2.0 "release notes"`
3. On an Intel Mac: same two commands (this merges the x86_64 entry into the
   same `latest.json`, carry the file between machines or re-run after both).
4. Create a GitHub Release tagged `v0.2.0` and upload:
   - `Lyre_aarch64.app.tar.gz` + `Lyre_x86_64.app.tar.gz` (updater packages)
   - `Lyre_aarch64.dmg` + `Lyre_x86_64.dmg` (first-install downloads)
5. Commit + push this `updates/latest.json` to `main`.

The running app compares its own version to `latest.json` `version` (semver) and,
if newer, downloads the matching platform package, verifies its minisign
signature against the pubkey in `tauri.conf.json`, installs, and relaunches.
