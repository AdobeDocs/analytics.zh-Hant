---
description: 在 Analysis Workspace 中使用快速區段。
title: 快速區段
feature: Segmentation
role: User, Admin
exl-id: 680e7772-10d3-4448-b5bf-def3bc3429d2
source-git-commit: 86fc28375d62d9f1d71d0b239ea0e2038fae47e4
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 100%

---

# 快速區段

您可以在專案中建立快速區段以迴避完整[區段產生器](/help/components/segmentation/segmentation-workflow/seg-build.md)的複雜性。快速區段

* 套用為[僅限專案區段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html#what-are-project-only-segments%3F)。
* 最多允許 3 個規則。
* 請勿容納巢狀容器或循序規則。

若要比較快速區段的功能和成熟的元件清單區段，請至[這裡](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md)。

以下是快速區段的影片概觀：

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## 先決條件

任何人都能建立「[!UICONTROL 快速區段]」。但是，您需要「[!UICONTROL 區段建立]」權限 (位於 [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools) 中)，才能儲存快速區段或是在「[!UICONTROL 區段產生器]」中將其開啟。

## 建立快速區段

在手繪多邊形表格中，請按一下面板標頭中的篩選器+ 圖示：

![](assets/quick-seg1.png)

從這個空白畫板設定快速區段：

![空白快速區段](assets/qs-blank-slate.png)

| 設定 | 說明 |
| --- | --- |
| 名稱 | 區段的預設名稱為區段中規則名稱的組合。您可重新命名區段。 |
| 包含/排除 | 您可在區段定義中包含或排除元件，但不能同時包含和排除。 |
| 點擊/造訪/訪客容器 | 快速區段僅包含一個[區段容器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html#section_AF2A28BE92474DB386AE85743C71B2D6)，讓您在區段中包含 (或從中排除) 維度/量度/日期範圍。[!UICONTROL 訪客]包含特定於訪客所有造訪次數和頁面檢視的總體資料。[!UICONTROL 造訪次數]容器可讓您設定規則，以根據造訪次數來劃分訪客的資料，而[!UICONTROL 點擊]容器則可讓您根據個別頁面檢視來劃分訪客資訊。 預設容器為[!UICONTROL 點擊]。 |
| 元件 (維度/量度/日期範圍) | 透過新增元件 (維度和/或量度和/或資料範圍) 及其值來定義最多 3 個規則。有 3 種方法可以找到正確的元件:<ul><li>開始輸入，然後[!UICONTROL 快速區段]產生器就會自動找到合適的元件。</li><li>使用下拉式清單來尋找元件。</li><li>從左側邊欄拖放元件。</li></ul> |
| 運算子 | 使用下拉式功能表尋找標準運算子和 [!UICONTROL Distinct Count] 運算子。[了解更多](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=zh-Hant) |
| 加 (+) 號 | 新增另一個規則 |
| AND/OR 限定詞 | 您可以對規則加入「AND」或「OR」的限定詞，但不能在單一區段定義中混合使用「AND」和「OR」。 |
| 套用 | 將此區段套用在面板上。如果區段不包含任何資料，系統將詢問您是否要繼續。 |
| 開啟產生器 | 開啟區段產生器。在「區段產生器」中儲存或套用區段後，將無法再考慮「快速區段」。它會成為元件清單區段資料庫的一部分。 |
| 取消 | 取消這個快速區段 - 不要套用它。 |
| 日期範圍 | 驗證器使用面板日期範圍進行資料查詢。但是在快速區段中套用的任何日期範圍都會覆蓋面板頂端的面板日期範圍。 |
| 預覽 (右上角) | 讓您查看是否有有效的區段以及區段的範圍。代表您套用此區段時可預期看到的資料集劃分。您可能會收到一則通知，指出此區段沒有資料。如果是這種情況，您可繼續或變更區段定義。 |

以下是結合維度和量度的區段範例:

![](assets/quick-seg2.png)

此區段會顯示在頂端。請注意，其藍色條紋的側邊欄和左側區段資料庫中元件級別區段的藍色側邊欄相反。

![](assets/quick-seg5.png)

## 編輯快速區段

1. 將滑鼠懸停在快速區段上，並選取鉛筆圖示。
1. 編輯區段定義和/或區段名稱。
1. 按一下[!UICONTROL 「套用」]。

## 儲存快速區段

>[!IMPORTANT]
>儲存或套用區段後，您將無法在「快速區段產生器」中對其進行編輯，而只能在一般的區段產生器中進行編輯。只有 Adobe Analytics 產品管理員和快速區段的建立者能夠儲存對現有快速區段的變更。

1. 套用快速區段後，將滑鼠懸停在上方，並選取資訊 (「i」) 圖示。

   ![](assets/quick-seg6.png)

1. 按一下&#x200B;**[!UICONTROL 「設為可用於所有專案，並新增至您的元件清單」]**。
1. (選擇性) 重新命名區段。
1. 按一下「**[!UICONTROL 儲存]**」。

請注意區段的側邊欄如何從藍色條紋變成淺藍色。它現在還會顯示在左側欄的元件清單中。

## 什麼是僅限專案的區段？

僅限專案區段指僅適用於建立該區段的目前專案的區段。您無法在其他專案中取得這些區段，且無法和其他使用者共用。它們主要用於快速探索您的資料，而無需在左側欄建立和儲存區段。僅限專案的區段能以快速區段或[臨時區段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/ad-hoc-segments.html)的形式在面板放置區域中建立。

如果在[!UICONTROL 區段產生器]中開啟僅限專案的區段，會顯示僅限專案的通知。如果您不勾選「使該區段可用於..」並按一下&#x200B;**[!UICONTROL 套用]**，則該區段仍維持為僅限專案的區段。附註：如果您套用區段產生器的快速區段，將無法在[!UICONTROL 快速區段產生器]中將其開啟。

![取消勾選僅限專案](assets/project-only-unchecked.png)

如果您勾選「使該區段可用於..」並按一下&#x200B;**[!UICONTROL 儲存]**，即可在左側欄元件清單中取得該區段，以用於其他專案。您也可以和區段管理員的其他使用者共用區段。

![勾選僅限專案](assets/project-only-checked.png)

## 已知問題

1. 建立一個包含 2 個項目快速區段，並將其&#x200B;**[!UICONTROL 儲存]** 為 Test1。
1. 按一下「**[!UICONTROL 另存新檔]**」，並將此快速區段儲存為 Test2。
1. 編輯 Test2 快速區段，並將其再度儲存為 Test2.
請注意，Test1 快速區段已被 Test2 修改。
