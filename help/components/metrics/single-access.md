---
title: 單次存取
description: 維度項目在造訪中未變更的次數。
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
source-git-commit: 6d2c278c5525c89b73c39bbfcedbe644806bf989
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 15%

---

# 單次存取

**[!UICONTROL 單次存取]** [量度](overview.md)會顯示適用的報告維度在整個造訪中僅包含單一值的造訪次數。 這是更廣泛、維度特定的[[!UICONTROL 單頁造訪次數]](single-page-visits.md)版本。 對於某些維度，如果您想要檢視某個維度在造訪期間僅設定一次的值，此量度將有所幫助。

## 此量度的計算方式

此量度的定義取決於[[!UICONTROL 計數重複執行個體]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings)的專案設定：

* **計算啟用的重複例項**：計算維度在一次造訪中只包含一個值的造訪。 如果維度持續存在，則不再符合單次存取的資格。
* **計算已停用的重複執行個體數**：計算維度包含單一不重複值的造訪次數。 您可以多次將維度專案設為相同值，或是讓維度專案持續存在，並且仍會計為單次存取。

不論&#39;[!UICONTROL 計算重複執行個體]&#39;為何，如果維度變更為第二個唯一值，該次造訪將不再符合單次存取的資格。 如果已在連結追蹤呼叫中設定維度，則此計算會包含連結追蹤呼叫。

## &#39;[!UICONTROL 單次存取]&#39;與&#39;[!UICONTROL 單頁造訪次數]&#39;之間的差異

在[[!UICONTROL 頁面]](../dimensions/page.md)維度的內容中，&#39;[!UICONTROL 單次存取]&#39;與&#39;[!UICONTROL 單頁造訪次數]&#39;一律完全相同，不論&#39;[!UICONTROL 計算重複執行個體數]&#39;專案設定為何。 當您使用其他維度時，兩者的差異就會顯現出來。

* **[!UICONTROL 單次存取]**：顯示單一點選出現指定維度專案的造訪次數。 此量度與您在專案中使用的維度相關。
* **[!UICONTROL 單頁造訪次數]**：顯示單一點選中有&#39;[!UICONTROL Page]&#39;維度的造訪次數。 即使您在報表中使用其他維度，此量度仍會計入包含單一不重複&#39;[!UICONTROL 頁面]&#39;維度專案的造訪。

如果停用[[!UICONTROL 計算重複執行個體]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings)，量度定義會稍微變更：

* **單次存取**：顯示指定的維度專案在整個造訪中未變更的造訪次數。
* **單頁造訪次數**：顯示&#39;[!UICONTROL 頁面]&#39;維度在整個造訪中未變更的造訪次數。

例如，請考量下列範例中的兩次點選造訪。 報表中的維度是[[!UICONTROL 網站區段]](../dimensions/site-section.md)，而且&#39;[!UICONTROL 計數重複執行個體]&#39;已停用。

* 訪客點擊了兩個頁面，但兩者位於相同的網站區段中。由於網站區段在造訪期間保持不變，因此會計為單次存取。 由於造訪包含多個唯一的[!UICONTROL 頁面]維度專案，因此不會計為單頁造訪次數。
* 訪客點擊了位於不同網站區段的兩個頁面，但這兩個頁面的名稱恰好相同。該次造訪不會計為單次存取，因為有兩個不重複的網站區段值。 由於有單一不重複的[!UICONTROL 頁面]維度專案，因此會計為單頁造訪次數。
