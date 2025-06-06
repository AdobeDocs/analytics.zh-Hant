---
description: 同步視覺效果可讓您控制哪些資料表或資料來源會對應至視覺效果。
keywords: Analysis Workspace, 將視覺效果同步至資料來源
title: 管理視覺效果資料來源
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
source-git-commit: 41ac4a97019e8192c96f3cdb141dad3d5db18d12
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 100%

---

# 管理視覺效果資料來源 {#manage-visualization-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="鎖定選取項目"
>abstract="啟用此設定，即可將視覺效果鎖定在資料來源中所選的位置或所選的項目。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="顯示表格"
>abstract="選取「**[!UICONTROL 顯示表格]**」將為您目前的視覺效果產生新的資料來源，並將其與原始資料來源分開。"

<!-- markdownlint-enable MD034 -->

同步視覺效果可讓您控制哪些資料表或資料來源會對應至視覺效果。

**秘訣：**&#x200B;您可以藉由標題旁的點色彩得知哪些視覺效果為相關。相符色彩表示視覺效果是根據相同的資料來源。

管理資料來源可讓您顯示資料來源或鎖定選取項目。這些設定會決定當新資料進入時視覺效果的變更方式 (或不變更)。

1. [建立專案](/help/analyze/analysis-workspace/home.md)，內含資料表和[視覺效果](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)。
1. 在資料表中，選取您想關聯至視覺效果的儲存格 (資料來源)。
1. 在視覺效果中，按一下標題旁的點可開啟&#x200B;**[!UICONTROL 「資料來源」]**&#x200B;對話方塊。選取&#x200B;**[!UICONTROL 「顯示資料來源」]**&#x200B;或&#x200B;**[!UICONTROL 「鎖定選取項目」]**。

   ![](assets/manage-data-source.png)

   將視覺效果同步至某個表格儲存格，會建立新的 (隱藏) 表格，並為同步的視覺效果及該表格設定色彩代碼。

## 資料來源設定




>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [資料來源設定](https://video.tv.adobe.com/v/23729?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]


| 元素 | 說明 |
| --- | --- |
| 連結的視覺效果 | 如果有連接至自由格式表格或同類群組表格的視覺效果，左上角的圓點會開啟，以列出連接的視覺效果，並以「顯示」核取方塊選項來顯示/隱藏此表格。游標暫留時會反白顯示連結的視覺效果，只要按一下，即可進入該視覺效果。 |
| 顯示資料來源 | 可讓您顯示 (勾選核取方塊) 或隱藏 (取消勾選) 對應至視覺效果的資料表。 |
| 鎖定選取項目 | 啟用此設定，將視覺效果鎖定至相對應資料表中目前選取的資料。啟用後，請選擇以下兩者其中之一：<ul><li>**選取的位置**：如果您要將視覺效果持續鎖定在從相對應資料表中選取的位置上，即可選擇此選項。即使這些位置中的特定項目已變更，這些位置仍將持續視覺化。例如，如果您想持續以此視覺效果顯示前五名的促銷活動名稱 (無論顯示在前五名的促銷活動名稱為何)，即可選擇此選項。</li><li>**選取的項目**：如果您要將視覺效果持續鎖定在相對應資料表中目前選取的特定項目上，即可選擇此選項。即使這些項目在表格中項目間的排名已變更，它們仍將持續視覺化。例如，如果您想持續以此視覺效果顯示相同的五個特定促銷活動名稱 (無論這些促銷活動名稱的排名為何)，即可選擇此選項。</li></ul> |

這個架構與舊版的不同之處，在於 Analysis Workspace 不會再建立重複的隱藏表格來儲存您的鎖定選取項目。資料來源現在會指出您建立視覺效果所用的表格。

## 範例使用案例

* 您可以建立摘要視覺效果，並將其鎖定至您建立視覺效果所用的表格中的儲存格。啟用「顯示資料來源」，便會顯示此資訊在表格上的確切位置。來源資料呈灰色：

  ![](assets/data-source2.png)>
* 您可以新增多個視覺效果，並使用相同表格中多個不同儲存格當成資料來源，如下所示。此表格與上方範例中的表格相同，但來源儲存格 (與量度) 不同：

  ![](assets/data-source3.png)>
* 您可以按一下左上角的圓點 (「資料來源設定」)，查看是否有連接至自由格式表格或同類群組表格的視覺效果。游標暫留時會反白顯示連結的視覺效果，只要按一下，即可進入該視覺效果。

  ![](assets/linked-visualizations.png)>
