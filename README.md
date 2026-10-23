<div align="center">

# 🍊 OrangeOS

**A new life for the Intel Mac macOS left behind.**

OrangeOS 1.0 “Valencia” · Debian 13 (Trixie) · amd64

[Download ISO](https://github.com/orangeos/orangeos/releases/latest) · [Documentation](docs/) · [Roadmap](docs/roadmap/) · [Report a bug](https://github.com/orangeos/orangeos/issues)

</div>

---

OrangeOS is a Debian Stable derivative for Intel Macs that no longer receive macOS updates. Its main goal is **Mac interaction compatibility**. Apple keyboards, Mac shortcuts, Magic Mouse and trackpad gestures, app switching, Spaces, the Dock and menu bar, Quick Look and the system settings all work the way Mac users expect. Everything is built from open-source components and carries original OrangeOS branding.

<!-- Replace with real screenshots, e.g. docs/assets/screenshots/desktop.png -->
<p align="center">
  <img src="docs/assets/screenshots/desktop.png" alt="OrangeOS desktop with menu bar, Dock and the Files app" width="800">
</p>

## Features

| Area | What you get |
| --- | --- |
| **Keyboard** | Apple keyboard layouts read as printed. ⌘ does what Command does, ⌥ handles accents and word navigation, ⌃ handles Spaces and terminal control. |
| **Shortcuts** | ⌘C / ⌘V, ⌘Q, ⌘Tab, ⌘\`, ⌘Space, ⇧⌘4 and ⌃↑, with the same meanings they have on a Mac. |
| **Trackpad & Magic Mouse** | Tap to click, natural two-finger scrolling and secondary click are configured on first boot. |
| **Gestures** | Three-finger swipe between Spaces, pinch to zoom, swipe up for an overview of every window. |
| **App-centric switching** | ⌘Tab switches applications, not windows. Closing the last window leaves the app running. |
| **Dock & menu bar** | App menus live in the top bar, and running apps are marked in the Dock. |
| **Quick Look** | Select a file and press Space to preview it. |
| **Settings** | Keyboard, Trackpad, Displays, Dock & Menu Bar and Spaces panes with familiar names and layout. |

## Supported hardware

OrangeOS 1.0 targets **Intel Macs from 2012 to 2017**.

A model counts as supported only after it passes the **Orange Mac Experience certification suite**. Newer Intel Macs are added through the same process. See [`docs/hardware/`](docs/hardware/) for the current certification list.

> Apple Silicon (M-series) Macs are not supported.

## Installing

1. **Download** the latest amd64 ISO from [Releases](https://github.com/orangeos/orangeos/releases/latest).
2. **Write it to a USB stick** with any disk-imaging tool (for example `dd`, balenaEtcher or GNOME Disks).
3. **Boot from it:** hold **⌥ Option** while the Mac starts and choose **EFI Boot**.
4. **Try it, then install:** the live session starts first. When networking, input, audio and display all work, click **Install**.

Detailed instructions are in [`docs/installer/`](docs/installer/).

## How updates work

```
deb.debian.org / security.debian.org ──┐
   Debian packages & security fixes    ├──► your Mac
Orange repository ─────────────────────┘
   Orange packages + scoped overrides
```

- **Debian packages come straight from Debian's repositories.** OrangeOS does not rebuild or mirror them, so security fixes arrive on Debian's schedule.
- **The Orange repository holds only** packages specific to OrangeOS and a small, narrowly scoped set of compatibility overrides.
- **Full upgrades keep Orange packages in place.**

See [`docs/packaging/`](docs/packaging/) and [`docs/release/`](docs/release/).

## Architecture at a glance

- **Base:** Debian 13 (Trixie), amd64
- **Desktop:** GNOME on Wayland, with selected parts extended or replaced by Orange components
- **Distribution:** live ISO with a guided installer

Full details are in [`docs/architecture/`](docs/architecture/) and [`docs/desktop/`](docs/desktop/).

## Non-goals

OrangeOS reproduces how a Mac **behaves**. It does not copy Apple's code or assets.

- No Apple proprietary assets or macOS binaries are redistributed.
- No firmware is shipped without redistribution rights.
- Apple services such as iMessage, FaceTime and Apple Pay are not supported and are not planned.

## Definition of Done for 1.0

On a supported Mac, OrangeOS 1.0 must:

- [ ] Boot the live ISO
- [ ] Install without manual Linux knowledge
- [ ] Bring up networking, input, audio and display
- [ ] Receive Debian security updates
- [ ] Keep Orange packages through full upgrades
- [ ] Pass the Orange Mac Experience certification suite

## Repository layout

| Path | Contents |
| --- | --- |
| [`docs/00-product-requirements.md`](docs/00-product-requirements.md) | Product requirements |
| [`docs/architecture/`](docs/architecture/) | System architecture |
| [`docs/compatibility/`](docs/compatibility/) | Mac interaction compatibility spec |
| [`docs/desktop/`](docs/desktop/) | Desktop components and behaviour |
| [`docs/hardware/`](docs/hardware/) | Hardware support and certification |
| [`docs/installer/`](docs/installer/) | Live ISO and installer |
| [`docs/packaging/`](docs/packaging/) | Packaging and repository policy |
| [`docs/build/`](docs/build/) | Building OrangeOS images |
| [`docs/ci/`](docs/ci/) | Continuous integration |
| [`docs/release/`](docs/release/) | Release process |
| [`docs/security/`](docs/security/) | Security policy and updates |
| [`docs/roadmap/`](docs/roadmap/) | Roadmap |
| [`claude/skills/`](claude/skills/) | Project skills for Claude Code |

## Contributing

Contributions are welcome, especially hardware test reports for Intel Macs in the 2012–2017 range. Before opening a pull request:

1. Read the [product requirements](docs/00-product-requirements.md) and the relevant spec in `docs/`.
2. Keep Debian packages unmodified wherever possible. Any override in the Orange repository needs a clear, narrow justification.
3. Never commit Apple proprietary code, artwork or firmware.

To report a security issue, follow [`docs/security/`](docs/security/) instead of opening a public issue.

## License

<!-- Add the project's license, e.g. GPL-3.0-or-later, and a LICENSE file -->
See [LICENSE](LICENSE).

---

<sub>OrangeOS is an independent open-source project and is not affiliated with Apple Inc. or the Debian Project. Mac, MacBook and iMac are trademarks of Apple Inc. Debian is a registered trademark of Software in the Public Interest, Inc.</sub>
