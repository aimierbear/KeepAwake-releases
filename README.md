# KeepAwake

**[English](README.md) · [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [日本語](README.ja.md) · [한국어](README.ko.md)**

A macOS menu-bar app that controls MacBook sleep behavior with two independent switches — keep your Mac awake with the lid closed, and block idle-triggered sleep while you work.

> 📦 **This repository distributes the signed + notarized `.dmg` only. The source code lives in a private repo.**

## ⬇️ Download

Latest release → **[KeepAwake-releases/releases/latest](../../releases/latest)**

Every `.dmg` is signed with Developer ID `C3SNXE45AV (Xiaoneng Wu)` and notarized by Apple. macOS Gatekeeper accepts it without the "downloaded from the internet" second-confirm dialog.

## 🧰 System Requirements

- macOS 14 Sonoma or later
- Apple Silicon or Intel

## ✨ Features

- **Lid-closed awake** — keep the Mac running when the lid is closed (one-time admin authorization required)
- **Prevent idle sleep** — suppress idle-triggered sleep while KeepAwake is running (IOKit assertion)
- **Auto-shutoff timer** — 30 min / 1 / 2 / 4 / 8 hours
- **Auto-start at login, remember last state, auto-reset switches on quit**
- **Crash-safe** — if the app dies, the helper auto-rolls `disablesleep` back to 0 after 60 s
- **15 languages** — follows the macOS system language

## 📥 Install

1. Download `KeepAwake-0.2.0.dmg` from the [latest release](../../releases/latest)
2. Double-click the DMG to mount, drag **KeepAwake.app** into `/Applications`
3. Launch from Launchpad or Applications
4. The first time you toggle "Lid-closed awake", macOS will ask permission to add a background item — click **Allow**

## 🔐 Signing & Notarization

- Developer ID: `Xiaoneng Wu (C3SNXE45AV)`
- Apple Notary Service: ✅ Accepted
- Stapled ticket (works offline, Gatekeeper can verify without a network)

## ⚠️ Closed-Lid Heat Risk — Please Read

**A MacBook's primary heat vent is under the keyboard.** When the lid is closed and the laptop rests flat on a surface, airflow is restricted. Running heavy workloads this way (video exports, compiles, ML training, long AI inference, games) can cause:

- CPU/GPU thermal throttling → your task actually runs *slower*
- Accelerated battery wear from prolonged high temperatures
- In extreme cases, thermal shutdown or hardware damage

**Use it safely:**

- ✅ Safe for **light** background tasks — file sync, downloads, keeping SSH/remote desktop alive, AirPlay receiving
- ⚠️ For **heavy** workloads with the lid closed, prop the laptop up or use a cooling stand. **Never** place it on a bed, blanket, couch, or inside a bag.
- ❌ Don't combine "lid closed + heavy load + blocked vents"

`Prevent idle sleep` also overrides battery-saving behavior. Turn it on when you need it, off when you don't.

**KeepAwake does not monitor temperature or load. Risk management is up to you.**

## 🔒 About the Source

The source repository is private. This repository exists only to distribute the signed + notarized DMG. If you need code-level access for audit or contribution, contact the author.

## License

Personal use.
