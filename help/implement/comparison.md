---
title: 比較實作方法
description: 了解將資料傳送至Adobe Analytics的各種方法的優點。
source-git-commit: 96a5daaf9d8358e4a5222a20f64c381cb8340ab1
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# 比較實作方法

查看每個實作Adobe Analytics的方法彼此相較之下的結果。 您可以使用此表格來協助貴組織判斷將資料傳送至Adobe的最理想方式。

|  | AppMeasurement | Adobe Analytics 擴充功能 | Web SDK | Web SDK擴充功能 |
| --- | --- | --- | --- | --- |
| 實作需求 | 參考 `AppMeasurement.js` 在每個頁面上，定義變數，使用 `s.t()` | 在每個頁面上參考標籤載入器，使用資料收集UI來定義變數並傳送資料至Adobe | 參考 `Alloy.js` 在每個頁面上，使用 `alloy("sendEvent",{})` 傳送包含所需資料的JSON物件 | 在每個頁面上參考標籤載入器，使用資料收集UI來建立JSON物件以傳送資料 |
| 資料目的地 | 直接傳送至Adobe Analytics | 直接傳送至Adobe Analytics | 傳送至Adobe Experience Platform Edge，將資料轉送至Adobe Analytics | 傳送至Adobe Experience Platform Edge，將資料轉送至Adobe Analytics |
| 執行調整困難 | 每次實作變更都需要存取網站程式碼 | 只需更改一次網站代碼即可安裝載入器標籤；資料收集UI中可進行所有進一步的實作更新 | 每次實作變更都需要存取網站程式碼 | 只需更改一次網站代碼即可安裝載入器標籤；資料收集UI中可進行所有進一步的實作更新 |
| 如何處理A4T | A4T呼叫包含在傳送至Adobe的點擊中 | A4T呼叫包含在傳送至Adobe的點擊中 | A4T呼叫會以個別點擊的形式傳送 | A4T呼叫會以個別點擊的形式傳送 |
| 如何處理反向連結 |