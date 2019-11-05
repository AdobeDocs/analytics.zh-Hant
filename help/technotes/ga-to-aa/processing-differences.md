---
title: Analytics平台之間的處理與架構差異
description: 瞭解Adobe Analytics和Google Analytics等平台之間收集和顯示的資料有何不同。
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Analytics平台之間的處理與架構差異

雖然Adobe Analytics和Google Analytics都是Analytics工具，但在不同平台間收集和處理資料的方式卻大不相同。 使用本頁可瞭解某些維度和量度的收集方式，以及為何在類似報表中顯示不同數字。

## 反彈率

「反彈率」是常見的KPI，用來協助評估大多數分析工具中著陸頁面的有效性和相關性。 這通常定義為進入網站但不包含點按至其他頁面的瀏覽。

* 在Adobe Analytics中，「反彈率」是使用公式「彈回數」除以「登 **入點」來計算**。
* 在Google Analytics中，「反彈率」是使用公式「單頁 **作業」除以「作業」來計算**。

在這兩種平台上，如果在相同的瀏覽或作業中傳送多個點擊，則不會視為彈回數。 在Adobe Analytics中，自訂連結是可用的，而且相當常見，可防止瀏覽計為彈回數。 Google Analytics通常不會在同一頁面上傳送多個資料要求。

若要在報告工具之間取得更佳的平衡，請使用Adobe Analytics中的「單頁瀏覽次數」量度，而不是「彈回數」作為計算量度的一部分。 「單頁瀏覽次數」度量包含僅包含單頁檢視的瀏覽總數，或進入網站但不包含點按至其他頁面的瀏覽總數。

如需詳細 [資訊，請參閱](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) 「元件」使用指南中的「反彈率」量度。

## 瀏覽與作業

瀏覽（在Google Analytics中稱為作業）是同一使用者在短時間內進行的頁面檢視群組。 兩種平台上的瀏覽通常會在閒置30分鐘後過期。 兩個平台都允許在瀏覽過期時進行自訂。 有幾種情況可能會導致每個平台的差異。

* **** 日終：Google Analytics中的所有工作階段都會在指定日的晚上11:59後到期。 如果使用者在12 AM後仍在您的網站上運作，則會建立新的工作階段。 Adobe Analytics會在次日繼續瀏覽，作為同次瀏覽的一部分。
* **** 不同的促銷活動：如果使用者的促銷活動來源變更，Google Analytics中就會開始新的工作階段。 如果Adobe Analytics中出現新的「追蹤代碼」值，則會視為同一次瀏覽的一部分。
* **** 手動作業覆寫：如果您使用手動啟動或結束作業，Google Analytics `sessionControl` 中會啟動新作業。 在Adobe Analytics中無法手動結束瀏覽。
* **** Adobe Analytics中的異常值瀏覽偵測：如果使用者在100秒內達到12小時的連續活動、2500次點擊或100次點擊，Adobe Analytics中的新瀏覽會自動開始。 這些偵測標準中的每個標準通常由機器人活動觸發。

如需詳細 [資訊，請參閱](/help/components/c-variables/c-metrics/metrics-visit.md) 「元件」使用指南中的「瀏覽」度量。
