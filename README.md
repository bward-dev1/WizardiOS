<div align="center">
  <h1>🧙 WizardiOS</h1>
  <strong>An all-in-one retro game emulator for iOS — multi-system, sideload-friendly, no placeholders.</strong>
  <br><br>
  <img src="https://img.shields.io/badge/platform-iOS%2015%2B%20%2F%20iPadOS-5b3aa0?style=flat-square" alt="iOS 15+">
  <img src="https://img.shields.io/badge/distribution-AltStore%20%2F%20SideStore-7c4dff?style=flat-square" alt="Sideload">
  <img src="https://img.shields.io/badge/license-AGPL%20v3-blue?style=flat-square" alt="AGPL v3">
</div>

---

## What this is

**WizardiOS is a fork of [Manic EMU](https://github.com/Manic-EMU/ManicEMU)** (AGPL-3.0),
rebranded and extended. It runs real, proven emulator cores — there are **no stub
cores**. Emulation is provided by RetroArch/libretro and dedicated cores, the same
engines Manic ships:

| System | Core |
|--------|------|
| Game Boy / Color | gambatte |
| Game Boy Advance | mGBA / vbam |
| Nintendo DS | melonDS / DeSmuME |
| Nintendo 3DS | Azahar (Citra lineage) |
| N64 | Mupen64Plus-Next |
| SNES / NES | bsnes / snes9x / Nestopia |
| PSP | PPSSPP |
| Genesis / Saturn / 32X / Sega CD | Genesis Plus GX / mednafen / PicoDrive |
| Dreamcast | Flycast |
| PSX | PCSX-ReARMed / mednafen |
| …and more | Atari, Lynx, Jaguar, Arcade (FBNeo/MAME), DOS, J2ME |

> WizardiOS ships **no** ROMs, ISOs, BIOS, or copyrighted game data. Use your own
> legally-owned backups, homebrew, and public-domain software only.

## What WizardiOS changes vs. Manic

- 🧙 **New identity** — WizardiOS name (home-screen + bundle id `com.wizardios.app`),
  original wizard app icon, and a wizard-purple accent applied app-wide (Manic shipped red).
- 🎨 **On-brand themes** — purple is the default theme, plus two new presets,
  **Mystic** and **Arcane**, in Settings → Theme.
- 🛠️ **Open CI builds** — every push builds an **unsigned `.ipa`** on GitHub's
  macOS runners (Xcode 26.4.1, real RetroArch + all cores). No Mac/Xcode needed to
  get an installable build — just download the artifact and sideload.
- _(ongoing)_ further feature/UX work over Manic, best iterated with the app
  installed on-device.

## Getting an installable build

This repo builds an **unsigned IPA** in CI:

1. Open the **Actions** tab → **Build WizardiOS IPA** → latest green run.
2. Download the **`WizardiOS-unsigned-ipa`** artifact.
3. Sideload it with **AltStore** or **SideStore** (signs with your free Apple ID).

📖 **Full step-by-step:** see [`INSTALL.md`](INSTALL.md) — loaders, JIT for 3DS/PSP,
importing games, and troubleshooting.

> 3DS/PSP and some cores rely on **JIT**, which on iOS requires sideloading
> (AltStore/SideStore) — the entitlements are already wired for it.

## Building locally

Requires a Mac with **Xcode 16+**, Git LFS, and submodules:

```bash
git clone --recurse-submodules https://github.com/bward-dev1/WizardiOS.git
cd WizardiOS && git lfs pull
open ManicEmu/ManicEmu.xcodeproj   # build the ManicEmuRelease scheme
```

## License & attribution

WizardiOS is **AGPL-3.0**, inherited from Manic EMU. All upstream copyright and
license notices are preserved. Core emulators are the property of their respective
projects — see [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md). Huge thanks to the
**Manic EMU** authors and the libretro/RetroArch community, on whose work this builds.

Upstream: https://github.com/Manic-EMU/ManicEMU
