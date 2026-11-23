<p align="center">
  <img src="images/icon.png" width="128" height="128" alt="Sable icon: a sculpted graphite leaf on a dark rounded tile">
</p>

<h1 align="center">Sable</h1>

<p align="center">
  <b>A native code editor, built in Rust.</b>
</p>

<p align="center">
  A fast, familiar editor with a file explorer, syntax highlighting, language servers,
  an integrated terminal, Git source control, tasks and a debugger.
  No AI panels, no telemetry, no Electron.
</p>

<p align="center">
  <a href="https://github.com/JobinBiju/sable-releases/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/JobinBiju/sable-releases?style=flat-square&label=latest&color=88c0d0"></a>
  <img alt="macOS and Linux" src="https://img.shields.io/badge/runs%20on-macOS%20%C2%B7%20Linux-555555?style=flat-square">
  <img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-555555?style=flat-square">
</p>

<p align="center">
  <a href="https://github.com/JobinBiju/sable-releases/releases/latest"><b>Download the latest release</b></a>
</p>

---

This repository holds Sable's downloads and the update information that Sable
reads to keep itself up to date. Each [release](https://github.com/JobinBiju/sable-releases/releases)
lists what changed.

## Download

Open the [latest release](https://github.com/JobinBiju/sable-releases/releases/latest)
and pick the file for your system:

| Your system | Download |
| --- | --- |
| Mac with Apple silicon (M1 and later) | `sable-<version>-macos-arm64.dmg` |
| Mac with Intel, or not sure | `sable-<version>-macos-universal.dmg` (runs on any Mac) |
| Debian, Ubuntu | `sable-<version>-linux-x86_64.deb` |
| Fedora, openSUSE | `sable-<version>-linux-x86_64.rpm` |
| Arch | `sable-<version>-linux-x86_64.pkg.tar.zst` |
| Any Linux | `sable-<version>-linux-x86_64.tar.gz` |

Mac builds also come as a `.zip` with the app inside. For 64-bit ARM Linux,
pick the same packages named `linux-aarch64`.

Windows builds will return in a later release.

## Install

### macOS

1. Open the `.dmg` and drag **Sable** to **Applications**.
2. Open Sable from Applications.

Sable is not yet notarized by Apple, so the first launch shows a warning that
macOS cannot check it. To open it anyway:

1. Try to open Sable once and close the warning.
2. Open **System Settings → Privacy & Security**.
3. Under *Security*, choose **Open Anyway** next to the message about Sable,
   and confirm.

You only need to do this once.

### Linux

Install the package with your package manager, for example:

```sh
sudo apt install ./sable-<version>-linux-x86_64.deb    # Debian, Ubuntu
sudo dnf install ./sable-<version>-linux-x86_64.rpm    # Fedora
sudo pacman -U sable-<version>-linux-x86_64.pkg.tar.zst  # Arch
```

Or extract the `.tar.gz` and run `./Sable`. Sable needs glibc 2.35 or newer
(Ubuntu 22.04, Debian 12, Fedora 36 and later), OpenGL or EGL, and X11 or
Wayland.

## Updates

On macOS, from version 0.2.14 on, Sable updates itself. It checks once a day, downloads a
new version in the background, and asks you to restart. Your open windows,
files and unsaved changes come back after the restart. You can also choose
**Sable → Check for Updates…** at any time.

In **Settings → Updates** you can turn off automatic checks or downloads, and
choose a channel:

- **Stable**: tested releases, recommended.
- **Preview**: earlier access to new features, which may be less stable.

If you have a version older than 0.2.14, download the latest release once by
hand; after that, updates arrive on their own.

On Linux, Sable tells you when a new version is out and opens the download;
install it the same way as the first time.

## Verify a download

Every release includes `SHA256SUMS.txt`. To check the files you downloaded,
run this in the folder that holds them:

```sh
shasum -a 256 -c SHA256SUMS.txt --ignore-missing
```

Each file should report `OK`.

Sable also checks updates on its own: `latest.json` lists every download with
its size and SHA-256, and `latest.json.sig` is an Ed25519 signature of that
file. Sable only installs an update when the signature matches the key built
into the app and the download matches its checksum.

## What you need

- **macOS 11 (Big Sur) or later**, on Apple silicon or Intel, or **Linux**
  with glibc 2.35 or newer on x86_64 or ARM64.
- **Git**, for source control (optional).
- **Language servers and formatters** for the languages you use (optional).
  Sable finds the ones you have installed; set them up in
  **Settings → Languages**.
- **A debug adapter** to debug programs (optional), such as `lldb-dap`, which
  comes with Xcode.

## Where Sable keeps your settings

Settings, recent folders and window state live in
`~/Library/Application Support/Sable` on macOS and `~/.config/sable` on Linux,
not inside the app. Updating or
reinstalling Sable keeps them.

## Feedback

Found a problem or have an idea? [Open an issue](https://github.com/JobinBiju/sable-releases/issues)
and include your Sable version (**Sable → About Sable**) and your system.

## License

Sable is open source under the MIT License.
