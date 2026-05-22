---
title: 複製處理規則
description: 瞭解如何將處理規則從一個報表套裝複製到另一個報表套裝。
feature: Processing Rules
role: Admin
exl-id: bb34ecac-0512-4cff-9ef0-72db2dcabc03
TQID: 'https://experienceleague.adobe.com/x7mG1fjpNiPn0x6No0RtEz4aJLcN2t7wpUkJ-0LQxII'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: fbaf7f9a-8341-44f6-aa57-6c8d50741804
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 253
ht-degree: 0%

---

# 在報表套裝之間複製處理規則

複製處理規則可讓您避免在多個報表套裝中手動重新建立相同的邏輯。 您可以使用複製功能，輕鬆將處理規則功能共用給許多報表套裝，或將測試的功能從開發報表套裝複製到生產報表套裝。

**[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** >選取報表套裝> **[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 處理規則]** > **[!UICONTROL 複製處理規則]**

此介面允許兩個選項：

* **取代所有處理規則**：此選項會從目的地報表套裝刪除所有處理規則，然後以相同順序將所有處理規則新增至目的地報表套裝。 您無法選取有限數量的處理規則來取代。
* **附加特定處理規則**：此選項可讓您選取一或多個處理規則。 附加的規則會新增至每個目標報表套裝的處理規則清單結尾。 將規則附加至每個目標報表套裝時，請考慮處理規則順序和已存在的規則。

選取要附加的處理規則或要複製到其中的報表套裝時，您可以使用`Ctrl`/`Cmd` + `Click`來選取多個處理規則或報表套裝。 選取要複製至的所需報表套裝後，選取「**[!UICONTROL 複製]**」並確認出現的強制回應視窗。

>[!WARNING]
>
>處理規則直接影響資料收集，如果使用不正確，可能會造成資料遺失。 將處理規則複製到生產報表套裝之前，請一律先在開發報表套裝中測試這些規則，以便緩解資料品質問題。
