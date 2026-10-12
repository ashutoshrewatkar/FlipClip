# 📎 Flip Clip

<p align="center">
  <img src="https://img.shields.io/badge/version-1.0.0-blue" alt="version" />
  <img src="https://img.shields.io/badge/platform-Supernote%20(Manta%2FNomad)-000000" alt="platform" />
  <img src="https://img.shields.io/badge/built%20with-React%20Native-61DAFB?logo=react&logoColor=white" alt="react native" />
  <img src="https://img.shields.io/badge/license-MIT-green" alt="license" />
</p>

> **Clip text & page regions from your reading, place them into your notes — and flip between your recent documents with one tap.**

Flip Clip is a utility plugin for Supernote devices (Manta/Nomad). It lets you capture
text and page **regions** from PDFs, e-books and notes, collects them into clipping lists,
and inserts them back into your note pages — with a drag-to-place box, a pre-insert erase
tool, and one-tap undo. It also adds an always-on-top floating button to flip between your
two most-recently-opened documents.

> **Flip Clip is a fork of [sn-clipper](https://github.com/vmnair/sn-clipper) by Vinod Nair, distributed under the MIT License.**
> The core clip → aggregate → insert engine is his work; this project adds the document-switch
> floating button, region/menu clipping, the erase/mask tool, drag-to-place insertion, and undo
> on top. See [`NOTICE`](NOTICE) and [`LICENSE`](LICENSE).

## Highlights

- **Floating switch button** — single-tap flips between your two most-recently-opened
  documents; **double-tap** opens the menu. Optionally **pin** one document (Browse) to
  override one side; **Clear** to go back to automatic. Drag to reposition (it edge-docks to
  the nearest side); it auto-hides outside the Note/Document apps.
- **Clip** — text and page **regions** from PDFs/e-books/notes; Picture & Text clipping lists;
  aggregate, merge, and jump back to the source.
- **Place, don't guess** — insert a single clip with a **drag-to-place box** (text or image):
  position it over existing content or clear of it, sized to fit.
- **Erase/mask** — white-out parts of an image clip **before** it goes into a note.
- **Undo** — one tap removes the last placement and restores the clip.
- **Table of Contents** generator for notes (from the original project).

## Install (sideload)

1. Download `flipclip.snplg` from the [Releases](../../releases) page (or build it — see below).
2. Copy it to your Supernote's **MyStyle** folder (USB/MTP), or download it on the device.
3. On the device: **Settings → Apps → Plugins → Add Plugin → select `flipclip.snplg`.**
   (On Manta/Nomad you can also use Settings → My Style → Sideloading.)
4. Open a note or document — Flip Clip's tools appear via its floating button and the Plugins toolbar.
5. When prompted, allow **"Display over other apps"** so the floating button can show, and grant
   file access when it first asks.

Requires a Supernote (Manta/Nomad) with plugin support.

## Privacy & permissions

- Declares only `FILE:READ` and `FILE:WRITE`. **No `INTERNET` permission — the plugin makes no
  network calls; all captures stay on your device.**
- Uses an always-on-top overlay for the floating button and checks which app is in the foreground
  so the button can auto-hide outside the Note/Document apps. On-device only.

## Build

Requires Node (≥18), JDK 21, and the Android SDK (platform 35 / build-tools 35.0.0).

```bash
# Windows (PowerShell)
./buildPlugin.ps1

# macOS/Linux
./buildPlugin.sh
```

Output: `build/outputs/flipclip.snplg`. The build runs the Jest suite, bundles the RN JS,
and runs the Gradle `buildCustomApkDebug` task (the plugin has native Kotlin modules).

## License & attribution

Flip Clip is released under the [MIT License](LICENSE). It is a fork of
[sn-clipper](https://github.com/vmnair/sn-clipper) by Vinod Nair (also MIT); his copyright is
retained in `LICENSE`, and modifications are described in [`NOTICE`](NOTICE).
