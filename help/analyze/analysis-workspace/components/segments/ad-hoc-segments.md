---
description: 在 Analysis Workspace 中使用臨時區段。
title: 臨時區段
feature: Segmentation
role: User, Admin
exl-id: 1c189abc-ab9f-413c-9be6-0d2fc457230e
source-git-commit: f50e3d9a1d3c1705c55a14af0e42a0da3ac00955
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 55%

---

# 臨時專案區段

即席項目段允許您直接將任何元件拖放到面板放置區中以建立段。 該段成為 [項目級段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?#what-are-project-only-segments%3F) 本地到當前項目。

以下是有關建立臨時專案區段的影片：

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

1. 將任何元件類型 (維度、維度項目、事件、量度、區段、區段範本、日期範圍) 拖放至面板頂端的區段托放區。元件類型會自動轉換為即席段或 [快速段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?lang=zh-Hant) 。
以下是如何為 Twitter 反向連結網域建立區段的範例：

   ![](assets/ad-hoc1.png)

   您的面板會自動套用此區段，而且您可以即刻看到結果。

1. 可以向面板添加無限數量的段。
1. 如果您決定要儲存此區段，請參閱以下章節。

請記住：

* 下列元件類型&#x200B;**無法**&#x200B;拖曳至區段拖放區域：計算量度以及無法建立區段的維度/量度。
* 為了取得完整的維度和事件，Analysis Workspace 會建立「存在」點擊區段。範例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
* 如將「未指定」或「無」拖放至區段拖放區，就會自動轉換成「不存在」區段，以便系統可正確處理區段。

要比較可在項目中建立和應用的不同段，請轉到 [這裡](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md)。

## 保存即席段 {#ad-hoc-save}

通過保存特定段，可以將其提供給其他項目。

1. 將滑鼠懸停在托放區中，並選取「i」圖示。
1. 按一下編輯鉛筆可轉到段生成器。
1. 檢查 **[!UICONTROL 使所有項目都可用並添加到元件清單]**。
1. 按一下 **[!UICONTROL 保存]**。

保存後，該段可在左滑軌元件清單中使用，並可與「段管理器」(Segment Manager)中的其他用戶共用。
