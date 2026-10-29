# xenon-releases

[Xenon](https://github.com/ThaRae/Xenon)'s releases for macOS and Linux, on Apple silicon with macOS 14.4 or later or x86 for linux. Each
[release](https://github.com/ThaRae/xenon-releases/releases) has `Xenon-<version>.tar.xz` and `Xenon-<version>.dmg`, which holds `Xenon.app`. Linux releases are as `Xenon-<version>.appimage`

## Installing

1. Download the newest release's `Xenon-<version>.tar.xz`, and open it to unpack `Xenon.app`.
2. Move `Xenon.app` to Applications.
3. Apple hasn't notarized Xenon, so macOS stops it the first time. Open it once from **System Settings → Privacy &
   Security → Open Anyway**, or run `xattr -dr com.apple.quarantine /Applications/Xenon.app`.

From then on, Xenon updates itself. **Settings → Updates** says when it last checked, and turns that off.

## The appcast

`appcast.xml` is the [Sparkle](https://sparkle-project.org) feed that Xenon checks for new versions, at
`https://raw.githubusercontent.com/ThaRae/xenon-releases/main/appcast.xml`. Xenon's `Meta/release.py publish` writes
it with each release, so don't edit it by hand.

The appcast and every archive are signed with Xenon's update key, whose public half is
`o7cmjh8R2wfWfRfJOTcyLisyoRVEEQIxi7L+SFWXUNI=`, and Xenon installs nothing else. The apps are signed with Xenon's own
certificate, **Xenon Release** (SHA-1 `EB4C4127CEA7DA5990952E139293BA15C0BA1D37`). `Documentation/Updates.md` in Xenon
describes how releases are made and checked.
