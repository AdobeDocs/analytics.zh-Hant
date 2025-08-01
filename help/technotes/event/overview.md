---
title: 分析受事件影響的資料
description: 了解受事件影響的資料對整體資料品質的貢獻。
exl-id: 8d81a432-42d6-4f5d-b66a-bb3af7fc4857
feature: Curate and Share
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 96%

---

# 分析受事件影響的資料

有時候，事件會影響組織中的資料品質。例如：

* 傳送離群值資料 (如數百萬美元收入) 的機器人
* 您的組織推送更新至您的網站，對您的 Analytics 實作造成負面影響
* 其他影響資料品質或完整性的問題

如果您的網站遇到任何資料品質問題，建議您將其排除在報告之外，避免對其做出業務決策。使用這些區段來評估事件對您資料的影響，並決定您要如何繼續。

## 判斷事件成因

如果您不確定為何會看到資料突然上升或下降，請參閱[疑難排解資料突然上升/下降](spikes-drops.md)。

## 使用細分分析和排除資料

Adobe Analytics 提供簡單而強大的方式，讓您使用細分來關注或排除資料。您可以使用區段中的日期範圍維度，篩選掉或關注這些特定日期。請參閱[在分析中排除特定日期](segments.md)。

## 將事件與先前的日期範圍比較

如果您想深入了解事件對您的資料隨著時間而產生的影響，可以在 Analysis Workspace 中使用日期比較功能。此功能可讓您逐日、逐週或逐月比較資料，以檢視其與先前範圍的比較結果。您接著可使用此比較結果來判斷事件對趨勢的影響程度。請參閱[將受事件影響的日期與先前的範圍比較](compare-dates.md)。

## 衍生使用計算量度的資料

建立區段並使用日期比較功能後，您就可以結合這兩個概念，使用計算量度來修正趨勢資料。在計算量度中加入區段，然後將受影響的日期乘於比較日期時發現的時間差異。請參閱[衍生受事件影響的資料](calcmetrics.md)。

## 與組織中的使用者溝通影響

準備好要如何處理事件後，就可以[與組織中的使用者溝通](communicate.md)。Adobe 在 Analytics 中提供數個位置，讓您放置文字，與使用者溝通發生的情況及他們可使用的元件。

## 影片

>[!BEGINSHADEBOX]

觀看![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [分析並傳達資料中的變數](https://video.tv.adobe.com/v/33316?quality=12&learn=on){target="_blank"}以取得示範影片。

* **0:27**：使用細分排除資料
* **2:55**：將事件與先前範圍比較
* **8:42**：衍生使用計算量度的資料
* **11:46**：與使用者溝通影響

>[!ENDSHADEBOX]


