# Installing WizardiOS 🧙

WizardiOS ships as an **unsigned `.ipa`**. You sign it with your own free Apple ID
at install time using a sideload loader. No paid developer account, no jailbreak.

> ⚠️ WizardiOS ships **no games, BIOS, or copyrighted data**. Use only your own
> legally-owned backups, homebrew, and public-domain software.

---

## 1. Get the IPA

**Option A — from CI (always latest):**
1. Open the repo's **Actions** tab → **Build WizardiOS IPA** → newest green run.
2. Download the **`WizardiOS-unsigned-ipa`** artifact and unzip it → `WizardiOS-unsigned.ipa`.

**Option B — local copy:** it's already at `dist/ipa/WizardiOS-unsigned.ipa` in this checkout.

> Artifacts expire after ~90 days. Re-run the workflow (Actions → Run workflow) any time to rebuild.

---

## 2. Pick a sideload loader

| Loader | Best for | Notes |
|--------|----------|-------|
| **SideStore** | On-device, no computer after setup | Uses a pairing file + on-device refresh. Recommended for JIT. |
| **AltStore (AltServer)** | Mac/PC nearby | Refreshes over Wi-Fi when computer is on the same network. |

Free Apple ID signing means the app **expires after 7 days** and must be refreshed
(both loaders can auto-refresh). A free Apple ID also caps you at **3 sideloaded apps**.

---

## 3. Install

### SideStore (recommended)
1. Install SideStore (see sidestore.io) and complete its one-time pairing setup.
2. SideStore → **My Apps** → **+** → select `WizardiOS-unsigned.ipa`.
3. Sign in with your Apple ID when prompted (used only to sign locally).
4. Wait for it to install; **WizardiOS** appears on your home screen.

### AltStore
1. Install AltServer on a Mac/PC, plug in the device, and install AltStore on the device.
2. On the device: AltStore → **My Apps** → **+** → pick `WizardiOS-unsigned.ipa`.
3. Enter your Apple ID to sign. Keep AltServer running to auto-refresh.

---

## 4. Enable JIT (needed for 3DS / PSP full speed)

The heavier cores (Azahar/3DS, PPSSPP/PSP) need **JIT** to run fast. The app already
ships the entitlements; you just have to *enable* JIT each launch on a free Apple ID:

- **SideStore:** long-press the app in SideStore → **Enable JIT** (or use its JIT toggle).
- **StikJIT / JitStreamer:** supported — the in-app JIT helper links out to it.
- Without JIT, lighter systems (GB/GBC/GBA/NES/SNES/Genesis/NDS) still play fine.

---

## 5. Add your games

1. Open **WizardiOS → Import** (middle tab).
2. Import ROMs/ISOs from **Files**, **iCloud Drive**, a **cloud service**, or over
   **Wi-Fi** (the app runs a local upload server — follow the on-screen address).
3. For systems that need BIOS (e.g. PSX, some others): **Settings → Advanced → BIOS**
   and add your own BIOS files.

---

## Troubleshooting

- **"Unable to install" / signing fails:** you may have hit the 3-app free-Apple-ID
  limit — remove another sideloaded app, or use an app-specific password if 2FA is on.
- **App crashes on launch right after the 7-day mark:** the signature expired — refresh
  it in SideStore/AltStore.
- **3DS/PSP runs slowly:** JIT isn't active — enable it (step 4) and relaunch the game.

Enjoy WizardiOS 🧙
