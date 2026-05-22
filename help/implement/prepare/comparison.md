---
title: 比較實施方法
description: 查看發送資料至 Adobe Analytics 的每種方法優點。
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/Tx3YIRJv4Qztv-Bsa9XJFMFVE0PW9SnvgrYeMmrULiA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 500
ht-degree: 40%

---

# 比較實施方法

查看每種實施 Adobe Analytics 方法之間的比較。 您可以使用這些表格來協助您的組織決定傳送資料給Adobe的最理想方式。 按一下每一欄以取得更具體的資訊。

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Adobe Analytics擴充功能](/help/implement/launch/overview.md) | [Web SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Web SDK擴充功能](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| 實施需求 | 在每個頁面上參考`AppMeasurement.js`、定義變數、使用`s.t()`傳送資料至Adobe Analytics | 在每個頁面上載入參考標籤載入器，使用資料收集UI來定義變數並傳送資料至Adobe Analytics | 在每個頁面上參考`Alloy.js`，使用`alloy("sendEvent",{})`來撰寫XDM物件，並使用Edge Network將所需的資料傳送到Adobe Analytics | 在每個頁面上，參考標籤載入器會使用資料收集UI來撰寫XDM物件，並使用Edge Network將所需的資料傳送到Adobe Analytics |
| 資料目的地 | 直接傳送到 Adobe Analytics | 直接傳送到 Adobe Analytics | 已傳送至 Adobe Experience Platform Edge，這可將資料傳送至 Adobe Analytics | 已傳送至 Adobe Experience Platform Edge，這可將資料傳送至 Adobe Analytics |
| 難以進行實施調整 | 每次實施變更都需要存取網站程式碼 | 變更網站程式碼一次，以安裝載入器標籤；所有進一步的實作更新都可在資料收集UI中進行 | 每次實施變更都需要存取網站程式碼 | 變更網站程式碼一次，以安裝載入器標籤；所有進一步的實作更新都可在資料收集UI中進行 |
| 如何處理 A4T | A4T 呼叫包含在傳送至 Adobe 的點擊中 | A4T 呼叫包含在傳送至 Adobe 的點擊中 | A4T 呼叫是以單獨點擊發送 | A4T 呼叫是以單獨點擊發送 |
| 內容資料 | 使用`s.contextData`。 | 在自訂程式碼區塊中使用`s.contextData` | 所有未對應的欄位會自動以`a.x.*`內容資料變數傳送。 | 所有未對應的欄位會自動以`a.x.*`內容資料變數傳送。 |

{style="table-layout:auto"}

## Mobile和其他

>[!CAUTION]
>
>版本 4 Mobile SDK 於 2021 年 8 月 31 日終止支援。 如需詳細資訊，請參閱[Adobe Mobile Services生命週期結束常見問題集](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html?lang=zh-Hant)。


| | [Mobile SDK](/help/implement/aep-edge/mobile-sdk/overview.md) | [Edge Network API](/help/implement/aep-edge/api/overview.md) |
| --- | --- | --- |
| 實施需求 | 在應用程式中載入參考標籤，然後在資料收集UI中使用直接API呼叫或規則來組成XDM物件，並使用Edge Network將所需的資料傳送至Adobe Analytics | 使用Edge Network API來撰寫XDM物件，並使用Edge Network將所需的資料傳送到Adobe Analytics |
| 資料目的地 | 已傳送至 Adobe Experience Platform Edge，這可將資料傳送至 Adobe Analytics | 已傳送至 Adobe Experience Platform Edge，這可將資料傳送至 Adobe Analytics |
| 難以進行實施調整 | 變更直接API呼叫所在的應用程式程式碼，或在資料收集UI中進行變更 | 每次實作變更都需要存取應用程式程式碼 |
| 如何處理 A4T | A4T 呼叫是以單獨點擊發送 | A4T 呼叫是以單獨點擊發送 |
| 內容資料 | 所有未對應的欄位會自動以`a.x.*`內容資料變數傳送。 | 所有未對應的欄位會自動以`a.x.*`內容資料變數傳送 |

{style="table-layout:auto"}
