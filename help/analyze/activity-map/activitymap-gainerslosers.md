---
description: 覆蓋圖提供多種設定資料視覺效果的方式，讓您輕鬆查看並了解頁面上連結的人氣高低。
seo-description: 覆蓋圖提供多種設定資料視覺效果的方式，讓您輕鬆查看並了解頁面上連結的人氣高低。
seo-title: 可自訂覆蓋圖
solution: Analytics
title: 可自訂覆蓋圖
topic: Activity Map
uuid: c1e56480-c1df-4a81-8a2a-42ea1362175c
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 可自訂覆蓋圖

覆蓋圖提供多種設定資料視覺效果的方式，讓您輕鬆查看並了解頁面上連結的人氣高低。

覆蓋圖可讓您在頁面上直接視覺化點按資料。This is what separates a visual analysis tool like [!DNL Activity Map] from mostly tabular and graphical tools like Reports &amp; Analytics.

[!DNL Activity Map] 提供三種覆蓋類型：

* 漸層覆蓋圖 (熱度圖)
* 氣泡覆蓋圖
* 獲益者和損失者覆蓋圖

您也可以[為動態內容設定覆蓋圖演算](/help/analyze/activity-map/activitymap-link-tracking/activitymap-stl-track-custom-elements.md)。

若要對覆蓋圖進行變更，請開啟「[覆蓋圖設定面板](/help/analyze/activity-map/activitymap-overlay-settings.md)」並編輯可用選項。

將滑鼠暫留在某個覆蓋圖上，會顯示其[詳細資料](/help/analyze/activity-map/activitymap-overlay-details.md)。

## Gradient overlay (Heatmap) {#section_06AF13DE05A1454D960176CD0DA921A6}

漸層覆蓋圖中的色彩強度是根據該連結的人氣高低。此強度可以針對前 30 名排行進行標準化，也可以做為絕對量度值的函數。

這些度量覆蓋在頁面的連結上，成為一種「熱圖」，提供重要問題的解答，其中包括：

* 個別頁面有何價值？
* 頁面上的個別元素有何價值?
* 頁面上最有價值的數位不動產為何?

![](assets/gradient.png)

## Bubble overlay {#section_A657AB3F64CB47F881BBFFD72B37D9D4}

氣泡覆蓋圖會在一個小型註標泡泡中顯示覆蓋圖內容 (量度、百分比或排名)。

在工具列的「覆蓋圖類型」中選取此覆蓋圖時，就會顯示氣泡覆蓋圖。Bubble overlays show for all links that match the selection in [[!DNL Activity Map] Settings](/help/analyze/activity-map/activitymap-overlay-settings.md) (top 30, top 50, all...). 如果未選取此選項，則顯示漸層覆蓋圖。

![](assets/bubble_overlay.png)

> [!NOTE] 子功能表的泡泡覆蓋圖只會在您顯示子功能表時顯示：
>
>![](assets/bubbles_submenu.png)&gt;

## Gainers and losers overlays {#section_EE80278E20C14824869BF5A27A4634C8}

**[!UICONTROL 獲益者和損失者覆蓋圖]** ，僅在即時模式中提供。 它們會比較目前時段的量度和上一個時段的量度，用以報告連結活動的即時變更。藉以提供充滿視覺吸引力的檢視即時趨勢方式。

此即時覆蓋圖會根據前一個和目前時段之間的量度值變更，來排名點按。

![](assets/gainers_losers.png)

