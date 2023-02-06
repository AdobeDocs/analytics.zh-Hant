---
title: 比較實施方法
description: 查看發送資料至 Adobe Analytics 的每種方法優點。
source-git-commit: 96a5daaf9d8358e4a5222a20f64c381cb8340ab1
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---

# 比較實施方法

查看每種實施 Adobe Analytics 方法之間的比較。 您可以利用此表幫助機構確定發送資料至 Adobe 的最理想方式。

|  | AppMeasurement | Adobe Analytics 擴充功能 | Web SDK | 網頁 SDK 擴充功能 |
| --- | --- | --- | --- | --- |
| 實施需求 | 在每個頁面參考 `AppMeasurement.js`、定義變量，使用 `s.t()` 發送資料 | 在每個頁面參考載入器標記，使用資料收集 UI 來定義並發送資料至 Adobe。 | 在每個頁面參考 `Alloy.js`，使用 `alloy("sendEvent",{})` 發送包含所需資料的 JSON 物件 | 在每個頁面參考載入器標記，使用資料收集 UI 來確定 JSON 物件並傳送資料 |
| 資料目的地 | 直接傳送到 Adobe Analytics | 直接傳送到 Adobe Analytics | 已傳送至 Adobe Experience Platform Edge，這可將資料傳送至 Adobe Analytics | 已傳送至 Adobe Experience Platform Edge，這可將資料傳送至 Adobe Analytics |
| 難以進行實施調整 | 每次實施變更都需要存取網站程式碼 | 網站程式碼只需要變更一次就可以安裝載入器標記；所有進一步的實施更新都可以在 資料收集 UI 中進行 | 每次實施變更都需要存取網站程式碼 | 網站程式碼只需要變更一次就可以安裝載入器標記；所有進一步的實施更新都可以在 資料收集 UI 中進行 |
| 如何處理 A4T | A4T 呼叫包含在傳送至 Adobe 的點擊中 | A4T 呼叫包含在傳送至 Adobe 的點擊中 | A4T 呼叫是以單獨點擊發送 | A4T 呼叫是以單獨點擊發送 |
| 如何處理反向連結 |