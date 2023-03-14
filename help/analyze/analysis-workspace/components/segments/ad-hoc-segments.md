---
description: 在Analysis Workspace中使用隨選區段。
title: 臨時區段
feature: Segmentation
role: User, Admin
exl-id: 1c189abc-ab9f-413c-9be6-0d2fc457230e
source-git-commit: 931e9b0bd71abd852c515cd2e7d99dc9ae423a63
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 77%

---

# 臨機專案區段

臨機專案區段可讓您直接將任何元件拖放至面板放置區以建立區段。 該區段成為目前專案的本機[專案層級區段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?lang=zh-Hant?#what-are-project-only-segments%3F)。

以下是關於建立臨機專案區段的影片：

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

1. 將任何元件類型 (維度、維度項目、事件、量度、區段、區段範本、日期範圍) 拖放至面板頂端的區段托放區。元件類型會自動轉換為臨機區段或 [快速區段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?lang=zh-Hant) 如果相容。
以下是如何為 Twitter 反向連結網域建立區段的範例：

   ![](assets/ad-hoc1.png)

   您的面板會自動套用此區段，而且您可以即刻看到結果。

1. 您可以對面板新增不限數量的區段。
1. 如果您決定要儲存此區段，請參閱以下章節。

請記住：

* 下列元件類型&#x200B;**無法**&#x200B;拖曳至區段拖放區域：計算量度以及無法建立區段的維度/量度。
* 為了取得完整的維度和事件，Analysis Workspace 會建立「存在」點擊區段。範例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
* 如將「未指定」或「無」拖放至區段拖放區，就會自動轉換成「不存在」區段，以便系統可正確處理區段。

若需比較您可以在專案內建立和套用的不同區段，請至[這裡](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md)。

## 儲存隨選區段 {#ad-hoc-save}

可儲存臨機區段供其他專案使用。

1. 將滑鼠停留在放置區域中，並按一下「i」圖示。
1. 按一下編輯鉛筆，即可前往區段產生器。
1. 勾選&#x200B;**[!UICONTROL 「設為可用於所有專案，並新增至您的元件清單」]**。
1. 按一下&#x200B;**[!UICONTROL 儲存]**。

儲存後，即可在左側欄元件清單中取得該區段，並可和區段管理員的其他使用者共用。
