---
title: Analytics平台之間的處理與架構差異
description: 瞭解如何在Adobe Analytics和Google Analytics等平台之間收集和顯示一些資料。
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# Analytics平台之間的處理與架構差異

雖然Adobe Analytics和Google Analytics都是Analytics工具，但在平台之間收集和處理資料的方式大不相同。使用此頁面可瞭解某些維度和度量的收集方式，以及為何在類似報表中顯示不同數字的原因。

## 反彈率

反彈率是通用KPI，用來協助測量大部分分析工具中著陸頁面的效用和相關性。這通常定義為進入網站但不包含點按其他頁面的瀏覽。

* In Adobe Analytics, Bounce Rate is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, Bounce Rate is calculated using the formula **Single-page sessions divided by Sessions**.

在這兩個平台上，如果同一次瀏覽或作業中傳送多次點擊，則不會視為彈回數。在Adobe Analytics中，自訂連結有可用且相當常見的情況，可防止瀏覽次數被計算為彈回數。Google Analytics通常不會在同一個頁面上傳送超過一個資料請求。

若要在報告工具之間達到更佳的一致性，請使用Adobe Analytics中的「單頁瀏覽次數」度量，而非「彈回數」做為計算度量的一部分。「單頁瀏覽次數」度量包括只包含一次頁面檢視的瀏覽總數，或進入網站但不包含點按其他頁面的瀏覽總數。

See the [Bounce Rate](../../components/c-variables/c-metrics/metrics-bounce-rate.md) metric in the Components user guide for more information.

## 瀏覽與作業

瀏覽(稱為Google Analytics中的作業)是同一使用者在短時間內進行的一組頁面檢視。這兩個平台上的瀏覽通常會在閒置30分鐘後過期。這兩個平台允許在瀏覽過期時自訂。有幾種情況可造成每個平台上的差異。

* **結束日期：** Google Analytics中的所有作業會在指定日期11：59PM之後過期。如果使用者在12AM後仍然活躍於您的網站，則會建立新作業。Adobe Analytics會在同一次瀏覽中繼續瀏覽至下一天。
* **不同的宣傳活動：** 如果使用者的促銷活動來源變更，Google Analytics中的新作業便會開始。如果在Adobe Analytics中看到新的追蹤代碼值，則會被視為同一次瀏覽的一部分。
* **手動作業覆蓋：** 如果您用 `sessionControl` 以手動開始或結束工作階段，Google Analytics中的新作業會開始。無法在Adobe Analytics中手動終止瀏覽。
* **Adobe Analytics中的異常瀏覽偵測：** 如果使用者在100秒內達到連續活動、2500次點擊或100次點擊，Adobe Analytics中的新瀏覽會自動開始。每個偵測標準通常由機器人活動觸發。

See the [Visits](../../components/c-variables/c-metrics/metrics-visit.md) metric in the Components user guide for more information.
