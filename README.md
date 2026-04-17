# KeepAwake — Public Release Downloads

A macOS menu-bar app that controls MacBook sleep behavior with two independent
switches (lid-closed awake + idle-sleep prevention).

**This repository is for distribution only — [每个 release 对应一个签名 + 公证的 DMG]. The source code is private.**

## Download

Grab the latest `.dmg` from [Releases](../../releases/latest).

All DMGs are signed with Developer ID `C3SNXE45AV (Xiaoneng Wu)` and notarized by Apple,
so macOS Gatekeeper will open them without "downloaded from internet" warnings.

## System Requirements

- macOS 14 Sonoma or later
- Apple Silicon or Intel

## Features

- **合盖不休眠** — keep the Mac awake when the lid is closed (requires one-time admin auth)
- **防空闲休眠** — prevent idle-triggered sleep
- **定时自动关闭** — 30 min / 1 / 2 / 4 / 8 h auto-shutoff
- Remember last state, auto-start on login, 15 languages

## ⚠️ 合盖运行过热风险

MacBook 散热口主要在键盘下方。合盖跑高负载任务（视频导出、编译、模型训练）可能导致 CPU/GPU 降频、电池加速老化、甚至触发热保护关机。

**请把 KeepAwake 限定在低负载后台任务（同步、下载、保持远程连接）**，高负载场景务必垫高笔记本或使用外接散热底座。

## License

Personal use.
