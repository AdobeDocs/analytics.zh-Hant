---
description: 同步視覺效果可讓您控制哪些資料表或資料來源會對應至視覺效果。
keywords: Analysis Workspace;Synchronize visualization with data source
title: 管理資料來源
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# 管理資料來源

同步視覺效果可讓您控制哪些資料表或資料來源會對應至視覺效果。

**秘訣：**&#x200B;您可以藉由標題旁的點色彩得知哪些視覺效果為相關。相符的色彩表示視覺化是以相同的資料來源為基礎。

管理資料來源可讓您顯示資料來源或鎖定選取範圍。 這些設定會決定當新資料傳入時，視覺化會如何變更（或不會變更）。

1. [建立專案](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)，內含資料表和[視覺效果](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)。
1. 在資料表中，選取您想關聯至視覺效果的儲存格 (資料來源)。
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. 選擇 **[!UICONTROL Show Data Source]** 或 **[!UICONTROL Lock Selection]**。

   ![](assets/manage-data-source.png)

   將視覺效果同步至某個表格儲存格，會建立新的 (隱藏) 表格，並為同步的視覺效果及該表格設定色彩代碼。

| 元素 | 說明 |
|--- |--- |
| 連結的視覺效果 | 如果有連接至自由表格或同類群組表格的視覺效果，左上角的圓點會開啟，列出連接的視覺效果，並以「顯示」核取方塊選項顯示/隱藏表格。暫留會反白標示連結的視覺化效果，按一下就會看到它。 |
| 顯示資料源 | 可讓您顯示（透過啟用核取方塊）或隱藏（透過停用）與視覺化對應的資料表格。 |
| 鎖定選擇 | 啟用此設定，可將視覺化鎖定至目前在對應資料表格中選取的資料。 啟用後，請選擇以下選項：  <ul><li>**選取的位置**：如果您要將視覺效果持續鎖定在從相對應資料表中選取的位置上，即可選擇此選項。縱使這些位置中的特定項目已變更，這些位置仍將持續視覺化。例如，如果您想要隨時顯示此視覺化中前5個促銷活動名稱，不論前5個促銷活動名稱顯示在哪些促銷活動名稱，請選擇此選項。</li> <li>**選取的項目**：如果您要將視覺效果持續鎖定在相對應資料表中目前選取的特定項目上，即可選擇此選項。縱使這些項目在表格中項目間的排名已改變，它們仍將持續視覺化。例如，如果您想要隨時在此視覺化中顯示相同的五個特定促銷活動名稱，不論這些促銷活動名稱排名在何處，請選擇此選項。</li></ul> |

這個架構與舊版的不同之處，在於 Analysis Workspace 不會再建立重複的隱藏表格來儲存您的鎖定選取項目。現在，資料來源會指向您從中建立視覺化的表格。

**範例使用案例：**

* 您可以建立摘要視覺化，並將其鎖定在您所建立表格中的儲存格。 當您啟用「顯示資料來源」時，它會確切顯示此資訊來自表格的位置。 來源資料會呈現灰色：

   ![](assets/data-source2.png)>
* 您可以新增許多視覺化，並從相同表格中的不同儲存格來尋找它們，如此處所示。 此表格與上方範例中的表格相同，但來源儲存格 (與量度) 不同：

   ![](assets/data-source3.png)>
* 按一下左上角的點（「資料來源設定」），即可查看是否有視覺化連接至自由表格或同類群組表格。 暫留功能會反白顯示連結的視覺化效果，按一下就會帶您前往。

   ![](assets/linked-visualizations.png)>
