---
description: 在Analysis Workspace中使用快速區段。
title: 快速區段
feature: Workspace Basics
role: User, Admin
source-git-commit: 51cac193cd2c88898139e079816a084c211a64f4
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 1%

---


# 快速區段

您可以在專案內建立快速區段，以略過完整[區段產生器](/help/components/segmentation/segmentation-workflow/seg-build.md)的複雜度。 快速區段

* 僅套用至建立專案的專案（您可以變更此項目）。
* 允許最多3個規則。
* 不容納巢狀容器或循序規則。
* 在具有多個報表套裝的專案中工作。

如需快速區段可以執行哪些動作與完整元件清單區段的比較，請前往[此處](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md)。

>[!IMPORTANT]
> 快速區段目前正在進行有限測試，目前尚未正式提供。

## 先決條件

任何人都可以建立[!UICONTROL 快速區段]。 不過，您需要[Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en#analytics-tools)中的[!UICONTROL 區段建立]權限，才能儲存快速區段或在[!UICONTROL 區段產生器]中開啟。

## 建立快速區段

在自由表格中，按一下面板標題中的「篩選+」圖示：

![](assets/quick-seg1.png)

| 設定 | 說明 |
| --- | --- |
| 名稱 | 區段的預設名稱是區段中規則名稱的組合。 您可以重新命名區段。 |
| 包含/排除 | 您可以在區段定義中包含或排除元件，但不能同時包括和排除元件。 |
| 點擊/造訪/訪客容器 | 快速區段僅包含一個[區段容器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html?lang=en#section_AF2A28BE92474DB386AE85743C71B2D6)，可讓您在區段中納入維度/量度/日期範圍（或將其排除在區段之外）。  訪客包含各瀏覽和頁面檢視的訪客特定整體資料。[!UICONTROL 瀏覽]容器可讓您設定規則，以根據瀏覽來劃分訪客的資料，而[!UICONTROL 點擊]容器則可讓您根據個別頁面檢視來劃分訪客資訊。 預設容器為[!UICONTROL Hit]。 |
| 元件(Dimension/量度/日期範圍) | 新增元件維度和/或量度及/或日期範圍及其值，以定義最多3個規則。 有3種方式可尋找正確的元件：<ul><li>開始輸入，[!UICONTROL 快速區段]產生器會自動找到適當的元件。</li><li>使用下拉式清單來尋找元件。</li><li>從左側邊欄拖放元件。</li></ul> |
| 運算元 | 使用下拉式功能表來尋找標準運算子和[!UICONTROL 不重複計數]運算子。 [了解更多](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=en) |
| 加號(+) | 新增其他規則 |
| 和/或限定符 | 您可以將「AND」或「OR」限定符新增至規則，但無法在單一區段定義中混合「AND」和「OR」。 |
| 套用 | 將此區段套用至面板。 如果區段不含任何資料，系統會詢問您是否要繼續。 |
| 開啟產生器 | 開啟區段產生器。 在「區段產生器」中儲存區段後，就不再視為「快速區段」。 它會成為元件清單區段庫的一部分。 |
| 取消 | 取消此快速段 — 不要應用它。 |
| 日期範圍 | 驗證器會使用面板日期範圍來進行資料查閱。 但快速區段中套用的任何日期範圍會覆寫面板頂端的面板日期範圍。 |
| 預覽（右上） | 可讓您查看您是否具備有效的區段，以及區段的廣度。 代表套用此區段時，您預期會看到的資料集劃分。 您可能會收到通知，指出此區段沒有資料。 您可以繼續或變更區段定義。 |

以下是結合維度和量度的區段範例：

![](assets/quick-seg2.png)

區段會顯示在頂端。 請注意其藍色條狀側邊欄，而非左側區段庫中元件層級區段的藍色側邊欄。

![](assets/quick-seg5.png)

## 編輯快速區段

1. 將滑鼠指標暫留在快速區段上，並選取鉛筆圖示。
1. 編輯區段定義或區段名稱。

## 儲存快速區段

您可以選擇在[!UICONTROL 快速區段產生器]或[!UICONTROL 區段產生器]中儲存快速區段。

>[!IMPORTANT]
>儲存或套用區段後，您就無法在「快速區段產生器」中編輯區段，只能在一般的區段產生器中編輯。

### 儲存至快速區段產生器

1. 套用快速區段後，將滑鼠指標暫留在該區段上並選取資訊(「i」)圖示。

   ![](assets/quick-seg6.png)

1. 按一下「**[!UICONTROL 讓所有專案都可用」並新增至元件清單]**。
1. （選用）重新命名區段。
1. 按一下「**[!UICONTROL 儲存]**」。

請注意區段的側邊欄如何從藍色條狀變更為藍色。 它現在會顯示在左側邊欄的元件清單中。


套用區段後，您可以選取將其新增至區段元件清單，並供所有專案使用。

1. 將滑鼠指標暫留在儲存的區段上，並選取鉛筆圖示。

1. 在「區段產生器」頂端，注意此對話方塊：

   ![](assets/project-only.png)

1. 選取&#x200B;**[!UICONTROL 讓此區段可供所有專案使用並新增至元件清單旁的核取方塊。]**
1. 按一下「**[!UICONTROL 儲存]**」。
1. 區段現在會顯示在您所有專案的區段元件清單中。
1. 您也可以[與組織中的其他人員共用區段](/help/components/segmentation/segmentation-workflow/t-seg-share.md)。

## 什麼是僅限專案的區段？

僅限專案的區段是快速區段或臨機工作區專案區段。 在[!UICONTROL 區段產生器]中編輯/開啟這些量度時，將會顯示僅限專案方塊。 如果您在產生器中套用快速區段，但未勾選「可用」方塊，則該區段仍為僅限專案的區段，但無法在[!UICONTROL 快速區段產生器]中開啟。 如果勾選該方塊並按一下&#x200B;**[!UICONTROL SAVE]**，它現在就是元件清單區段。