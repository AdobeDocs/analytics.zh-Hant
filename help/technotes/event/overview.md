---
title: 分析受事件影響的資料
description: 了解受事件影響的資料對整體資料品質的貢獻。
exl-id: 8d81a432-42d6-4f5d-b66a-bb3af7fc4857
feature: Curate and Share
TQID: https://experienceleague.adobe.com/DJoJwtp9CkgrCfA1DwW8rKX2x3ssfzLCo7vCfhdLusg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 404
ht-degree: 91%

---

# 分析受事件影響的資料

有時候，事件會影響組織中的資料品質。 例如：

* 傳送離群值資料 (如數百萬美元收入) 的機器人
* 您的組織推送更新至您的網站，對您的 Analytics 實作造成負面影響
* 其他影響資料品質或完整性的問題

如果您的網站遇到任何資料品質問題，建議您將其排除在報告之外，避免對其做出業務決策。 使用這些區段來評估事件對您資料的影響，並決定您要如何繼續。

## 判斷事件成因

如果您不確定為何會看到資料突然上升或下降，請參閱[疑難排解資料突然上升/下降](spikes-drops.md)。

## 使用細分分析和排除資料

Adobe Analytics 提供簡單而強大的方式，讓您使用細分來關注或排除資料。 您可以使用區段中的日期範圍維度，篩選掉或關注這些特定日期。 請參閱[在分析中排除特定日期](segments.md)。

## 將事件與先前的日期範圍比較

如果您想深入了解事件對您的資料隨著時間而產生的影響，可以在 Analysis Workspace 中使用日期比較功能。 此功能可讓您逐日、逐週或逐月比較資料，以檢視其與先前範圍的比較結果。 您接著可使用此比較結果來判斷事件對趨勢的影響程度。 請參閱[將受事件影響的日期與先前的範圍比較](compare-dates.md)。

## 衍生使用計算量度的資料

建立區段並使用日期比較功能後，您就可以結合這兩個概念，使用計算量度來修正趨勢資料。 在計算量度中加入區段，然後將受影響的日期乘於比較日期時發現的時間差異。 請參閱[衍生受事件影響的資料](calcmetrics.md)。

## 與組織中的使用者溝通影響

準備好要如何處理事件後，就可以[與組織中的使用者溝通](communicate.md)。 Adobe 在 Analytics 中提供數個位置，讓您放置文字，與使用者溝通發生的情況及他們可使用的元件。

## 影片

>[!BEGINSHADEBOX]

觀看![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [分析並傳達資料中的變數](https://video.tv.adobe.com/v/33316?quality=12&learn=on){target="_blank"}以取得示範影片。

* **0:27**：使用細分排除資料
* **2:55**：將事件與先前的範圍比較
* **8:42**：衍生使用計算量度的資料
* **11:46**：與使用者溝通影響

>[!ENDSHADEBOX]


