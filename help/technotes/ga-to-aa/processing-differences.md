---
title: Analytics 平台之間的處理與架構差異
description: 瞭解 Adobe Analytics 和 Google Analytics 等平台之間收集和顯示的資料有何不同。
translation-type: ht
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Analytics 平台之間的處理與架構差異

雖然 Adobe Analytics 和 Google Analytics 都是分析工具，但在不同平台之間，收集和處理資料的方式卻大不相同。本頁有助瞭解特定維度和量度之收集方式的主要差異，以及其為何在類似報表中顯示不同數字。

## 反彈率

「跳出率」是常見的 KPI，在大多數分析工具中，可用來協助評估登陸頁面的效益和相關性。這通常定義為進入網站的造訪，但不包含點按至其他頁面。

* 在 Adobe Analytics 中，「跳出率」是使用公式&#x200B;**「跳出數」除以「登入點」**&#x200B;來計算。
* 在Google Analytics中，「跳出率」是使用公式&#x200B;**「單頁工作階段」除以「工作階段」**&#x200B;來計算。

在這兩種平台上，如果在相同的造訪或工作階段中傳送多個點擊，則不會視為跳出。在 Adobe Analytics 中，自訂連結不但可用而且相當常見，可防止將造訪計入跳出數。Google Analytics 通常不會在同一個頁面上傳送多個資料請求。

若要在報表工具之間取得更佳的平衡，請使用 Adobe Analytics 中的「單頁造訪次數」量度，而不是「跳出數」作為計算量度的一部分。「單頁造訪次數」量度包括僅含單頁檢視的造訪總數，或進入網站但不包含點按至其他頁面的造訪。

如需詳細資訊，請參閱「元件」使用指南中的[跳出率](/help/components/c-variables/c-metrics/metrics-bounce-rate.md)量度。

## 造訪與工作階段

造訪 (在 Google Analytics 中稱為「工作階段」) 是同一位使用者在短時間內進行的一系列頁面檢視。兩種平台上的造訪通常會在閒置 30 分鐘後過期。兩個平台都允許在造訪過期時進行自訂。有數種情況可能會導致每個平台的差異。

* **一天結束時：** Google Analytics 中的所有工作階段都會在指定一日的晚上 11:59 後到期。如果使用者於午夜 12 點 後仍在您的網站上處於作用中狀態，則會建立新的工作階段。Adobe Analytics 會將造訪延續至隔日，作為同次造訪的一部分。
* **不同的促銷活動：**&#x200B;如果使用者的促銷活動來源變更，則 Google Analytics 中就會開始新的工作階段。如果 Adobe Analytics 中出現新的「追蹤程式碼」值，則會視為同一次造訪的一部分。
* **手動工作階段覆蓋：**&#x200B;如果您使用 `sessionControl` 來手動啟動或結束工作階段，則 Google Analytics 中會啟動新的工作階段。在Adobe Analytics中無法手動結束造訪。
* **Adobe Analytics 中的極端值造訪偵測：**&#x200B;如果使用者達到 12 小時的連續活動、2500 次點擊，或在 100 秒內達到 100 次點擊，Adobe Analytics 中的新造訪會自動開始。這些偵測標準通常是由機器人活動所觸發。

如需詳細資訊，請參閱「元件」使用指南中的[造訪](/help/components/c-variables/c-metrics/metrics-visit.md)量度。
