---
description: 在 Analysis Workspace 中使用臨時區段。
title: 臨時區段
feature: Workspace Basics
role: User, Admin
source-git-commit: f3185f1ee341348fb7bdbaab8b68d421e7c79076
workflow-type: ht
source-wordcount: '369'
ht-degree: 100%

---


# 臨時專案區段

以下是有關建立臨時專案區段的影片：

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

如果您想在不前往「區段產生器」的情況下快速探索區段可能影響您的專案的方式，您可以建立臨時專案區段。將這些區段視為臨時的、專案級別的區段。這些區段通常不會像左側邊欄中的元件區段那樣成為您的區段「庫」的一部分。但是，您可以將其儲存，如下所示。

若要比較臨時專案區段的功能和成熟的元件級別區段，請至[這裡](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md)。

1. 將任何元件類型 (維度、維度項目、事件、量度、區段、區段範本、日期範圍) 拖放至面板頂端的區段托放區。元件類型會自動轉換成區段。
以下是如何為 Twitter 反向連結網域建立區段的範例：

   ![](assets/ad-hoc1.png)

   您的面板會自動套用此區段，而且您可以即刻看到結果。

1. 您可以對面板新增不限數量的元件。
1. 如果您決定要儲存此區段，請參閱以下章節。

請記住：

* 下列元件類型&#x200B;**無法**&#x200B;拖曳至區段拖放區域：計算量度以及無法建立區段的維度/量度。
* 為了取得完整的維度和事件，Analysis Workspace 會建立「存在」點擊區段。範例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
* 如將「未指定」或「無」拖放至區段拖放區，就會自動轉換成「不存在」區段，以便系統可正確處理區段。

>[!NOTE]
>
>此為專案內部專用的區段建立方式。

## 儲存臨時專案區段 {#ad-hoc-save}

您可選擇完成以下步驟以儲存這些區段：

1. 將滑鼠懸停在托放區中，並選取「i」圖示。
1. 在顯示的資訊面板中，按一下「**[!UICONTROL 儲存]**」。

   ![](assets/segment-info.png)

## 什麼是僅限專案的區段？

僅限專案的區段指快速區段或臨時工作區專案區段。在區段產生器中編輯/開啟區段時，僅限專案方框就會顯示。如果在產生器中套用了快速區段但沒有勾選使其可用方框，那麼這仍然是一個僅限專案的區段，但卻無法再在 QS 產生器中開啟。如果勾選了上述方框並儲存，則現在是一個元件清單區段。