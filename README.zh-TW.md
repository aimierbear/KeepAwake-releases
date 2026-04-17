# KeepAwake

**[English](README.md) · [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [日本語](README.ja.md) · [한국어](README.ko.md)**

一款 macOS 選單列小工具，用兩個獨立開關精準控制 Mac 的睡眠行為——闔蓋繼續執行、阻擋閒置觸發的睡眠。

> 📦 **本儲存庫僅提供簽章 + 公證後的 `.dmg` 下載。原始碼位於私有儲存庫。**

## ⬇️ 下載

最新版本 → **[KeepAwake-releases/releases/latest](../../releases/latest)**

所有 `.dmg` 皆以 Developer ID `C3SNXE45AV (Xiaoneng Wu)` 簽章，並通過 Apple 公證。macOS Gatekeeper 會直接放行,不會跳出「從網際網路下載」的二次確認視窗。

## 🧰 系統需求

- macOS 14 Sonoma 或更新版本
- Apple Silicon 或 Intel 皆可

## ✨ 功能

- **闔蓋不休眠** — 闔上螢幕後 Mac 繼續執行(首次需一次性管理員授權)
- **防閒置休眠** — KeepAwake 執行期間阻擋閒置觸發的系統休眠(IOKit assertion)
- **定時自動關閉** — 30 分鐘 / 1 / 2 / 4 / 8 小時可選
- **開機自動啟動、記住上次狀態、結束時自動關閉開關**
- **當機自動還原** — 主 App 當機 60 秒後,helper 自動把 `disablesleep` 還原為 0
- **15 種語言** — 跟隨系統語言自動切換

## 📥 安裝

1. 從[最新 release](../../releases/latest) 下載 `KeepAwake-0.2.0.dmg`
2. 雙擊 DMG 掛載,將 **KeepAwake.app** 拖進 `/Applications`
3. 從 Launchpad 或應用程式啟動
4. 首次開啟「闔蓋不休眠」時,macOS 會提示加入背景項目,點**允許**

## 🔐 簽章 & 公證

- Developer ID:`Xiaoneng Wu (C3SNXE45AV)`
- Apple 公證:✅ 已通過
- Stapled ticket(離線環境也可被 Gatekeeper 驗證)

## ⚠️ 闔蓋運作過熱風險 — 請務必閱讀

**MacBook 的主要散熱口在鍵盤下方**。闔蓋後底殼貼在桌面,氣流被擋住,此時若執行高負載任務(影片匯出、編譯、模型訓練、長時間 AI 推論、遊戲)可能導致:

- CPU/GPU 持續降頻 → 你的任務反而**變慢**
- 長時間高溫,電池加速老化
- 極端情況下系統自動關機,甚至硬體損傷

**安全使用建議:**

- ✅ 闔蓋適合**低負載**背景任務——檔案同步、下載、保持 SSH / 遠端桌面、AirPlay 接收
- ⚠️ 闔蓋前如需執行重度任務,**務必**墊高筆電或使用散熱底座。**不要**放在床、毯子、沙發或塞進包包裡。
- ❌ 不要「闔蓋 + 高負載 + 堵住通風口」三件事同時發生

`防閒置休眠` 也會阻擋系統省電策略。按需開啟、用完關閉,別讓電池被無謂消耗。

**KeepAwake 不偵測溫度和負載。風險控管在你自己手裡。**

## 🔒 關於原始碼

原始碼儲存庫為私有。本儲存庫僅用於分發簽章 + 公證後的 DMG。如需程式碼層級存取以進行稽核或貢獻,請聯絡作者。

## License

僅供個人使用。
