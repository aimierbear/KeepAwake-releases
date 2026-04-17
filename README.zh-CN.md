# KeepAwake

**[English](README.md) · [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt-BR.md) · [Italiano](README.it.md)**

一款 macOS 菜单栏小工具，用两个独立开关精确控制 Mac 的睡眠行为——合盖继续运行、阻止空闲触发的睡眠。

> 📦 **本仓库只提供签名 + 公证后的 `.dmg` 下载。源码放在私有仓库。**

## ⬇️ 下载

最新版本 → **[KeepAwake-releases/releases/latest](../../releases/latest)**

所有 `.dmg` 都使用 Developer ID `C3SNXE45AV (Xiaoneng Wu)` 签名，并通过 Apple 公证。macOS Gatekeeper 直接放行，不会弹出「来自互联网」的二次确认。

## 🧰 系统要求

- macOS 14 Sonoma 或更新
- Apple Silicon 或 Intel 均可

## ✨ 功能

- **合盖不休眠** — 合上盖子后 Mac 继续运行（首次需一次性管理员授权）
- **防空闲休眠** — KeepAwake 运行期间阻止空闲触发的系统睡眠（IOKit assertion）
- **定时自动关闭** — 30 分钟 / 1 / 2 / 4 / 8 小时可选
- **开机自启动、记住上次状态、退出时自动关闭开关**
- **崩溃自动回退** — 主 App 崩溃 60 秒后，helper 自动把 `disablesleep` 还原为 0
- **15 种语言** — 跟随系统语言自动切换

## 📥 安装

1. 从[最新 release](../../releases/latest) 下载 `KeepAwake-0.2.0.dmg`
2. 双击 DMG 挂载，把 **KeepAwake.app** 拖进 `/Applications`
3. 从 Launchpad 或应用程序启动
4. 首次开启「合盖不休眠」时，macOS 会提示添加后台项目，点**允许**

## 🔐 签名 & 公证

- Developer ID：`Xiaoneng Wu (C3SNXE45AV)`
- Apple 公证：✅ 已通过
- Stapled ticket（离线环境也可被 Gatekeeper 验证）

## ⚠️ 合盖运行过热风险 — 请务必阅读

**MacBook 的主要散热口在键盘下方**。合盖后底壳贴在桌面，气流被挡住，这时再跑高负载任务（视频导出、编译、模型训练、长时间 AI 推理、游戏）可能导致：

- CPU/GPU 持续降频 → 你的任务反而**变慢**
- 长时间高温，电池加速老化
- 极端情况下系统自动关机，甚至硬件损伤

**安全使用建议：**

- ✅ 合盖适合**低负载**后台任务——文件同步、下载、保持 SSH / 远程桌面、AirPlay 接收
- ⚠️ 合盖前如需跑重活，**务必**垫高笔记本或使用散热底座。**不要**放在床、毯子、沙发或塞进包里。
- ❌ 不要「合盖 + 高负载 + 堵住通风口」三件事同时发生

`防空闲休眠` 也会阻止系统省电策略。按需开启、用完关闭，别让电池被无辜消耗。

**KeepAwake 不检测温度和负载。风险控制在你自己手里。**

## 🔒 关于源码

源码仓库私有。本仓库仅用于分发签名 + 公证后的 DMG。如需代码审计或贡献，请联系作者。

## License

仅供个人使用。
