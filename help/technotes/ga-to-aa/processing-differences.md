---
title: Analytics 平台之間的處理與架構差異
description: 瞭解 Adobe Analytics 和 Google Analytics 等平台之間收集和顯示的資料有何不同。
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 66%

---


# Analytics 平台之間的處理與架構差異

雖然 Adobe Analytics 和 Google Analytics 都是分析工具，但在不同平台之間，收集和處理資料的方式卻大不相同。本頁有助瞭解特定維度和量度之收集方式的主要差異，以及其為何在類似報表中顯示不同數字。

## [!UICONTROL 反彈率]

[!UICONTROL 「跳出率」是常見的 KPI，在大多數分析工具中，可用來協助評估登陸頁面的效益和相關性。]這通常定義為進入網站的造訪，但不包含點按至其他頁面。

* In Adobe Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Single-page sessions divided by Sessions**.

在這兩種平台上，如果在相同的造訪或工作階段中傳送多個點擊，則不會視為跳出。在 Adobe Analytics 中，自訂連結不但可用而且相當常見，可防止將造訪計入跳出數。Google Analytics 通常不會在同一個頁面上傳送多個資料請求。

To achieve better parity between reporting tools, use the [!UICONTROL Single Page Visits] metric in Adobe Analytics instead of [!UICONTROL Bounces] as part of a calculated metric. The [!UICONTROL Single Page Visits] metric includes the total number of visits that only included one-page view, or visits that enter the website but do not include a click to another page.

如需詳細資訊，請參閱「元件」使用指南中的[跳出率](/help/components/c-variables/c-metrics/metrics-bounce-rate.md)量度。

## [!UICONTROL 造訪與工作階段]

[!UICONTROL 瀏覽] （在Google Analytics中稱為作業）是同一使用者在短時間內進行的頁面檢視群組。 [!UICONTROL 兩種平台上的造訪通常會在閒置 30 分鐘後過期。]Both platforms allow customization on when a [!UICONTROL Visit] expires. 有數種情況可能會導致每個平台的差異。

* **一天結束時：** Google Analytics 中的所有工作階段都會在指定一日的晚上 11:59 後到期。如果使用者於午夜 12 點 後仍在您的網站上處於作用中狀態，則會建立新的工作階段。Adobe Analytics 會將造訪延續至隔日，作為同次造訪的一部分。
* **不同的促銷活動：**&#x200B;如果使用者的促銷活動來源變更，則 Google Analytics 中就會開始新的工作階段。If a new [!UICONTROL Tracking Code] value is seen in Adobe Analytics, it is considered part of the same visit.
* **手動工作階段覆蓋：**&#x200B;如果您使用 `sessionControl` 來手動啟動或結束工作階段，則 Google Analytics 中會啟動新的工作階段。[!UICONTROL 在Adobe Analytics中無法手動結束造訪。]
* **Adobe Analytics中的異常值瀏覽偵測：** 如果使 [!UICONTROL 用者在] 100秒內達到12小時的連續活動、2500次點擊或100次點擊，Adobe Analytics中的新瀏覽會自動開始。 這些偵測標準通常是由機器人活動所觸發。

如需詳細資訊，請參閱「元件」使用指南中的[造訪](/help/components/c-variables/c-metrics/metrics-visit.md)量度。
