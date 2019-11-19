---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 8deec068fcea49f1183633826d5ce8271fb38a14

---



# s.useForcedLinkTracking

此標幟用來停用某些瀏覽器的強制連結追蹤。依預設會為 FireFox 20 (和更高版本) 與 WebKit 瀏覽器啟用強制連結追蹤。

When `useForcedLinkTracking` is enabled, the AppMeasurement file overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. AppMeasurement檔案會執行追蹤連結呼叫並手動處理導覽事件，而非使用預設的瀏覽器動作。

JavaScript H.25.4 (於 2013 年 2 月發行) 針對在 `useForcedLinkTracking` 啟用時受到追蹤的連結新增了下列範圍限制。自動強制連結追蹤僅套用於:

* `<A>` 和 `<AREA>` 標籤實施流量分類。
* 標記必須具有 `HREF` 屬性.
* The `HREF` can't start with `#`, `about:`, or `javascript:`.
* The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`).

Default value = `true`

## 範例

`s.useForcedLinkTracking = false`
