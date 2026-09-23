---
title: 顯示器解析度
description: 訪客螢幕的解析度 (以像素為單位)。
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
TQID: https://experienceleague.adobe.com/d3AuMT0seRbZpuKVGPeWo98Bkhc8tcJIP6gt4y-rq38
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 51%
---
# 顯示器解析度

「監視器解析度」[維度](overview.md)以畫素顯示使用中顯示器的高度和寬度。 若您想了解網站上的「折頁」在什麼位置向訪客顯示，或是訪客可將瀏覽器視窗調整到多寬，這個維度相當實用。 瞭解折頁的位置可讓您將內容最佳化以供檢視。

此維度與瀏覽器[高度](browser-height.md)和[寬度](browser-width.md)不同。 瀏覽器高度/寬度是可檢視瀏覽器空間內的像素數，而螢幕解析度是整個螢幕的像素數。 如果您想在自己的電腦上觀察這兩個變數之間的差異，請開啟瀏覽器主控台 (在大部分的瀏覽器上為 F12)，並將下列程式碼複製並貼到主控台中：

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

瀏覽器維度一律小於螢幕解析度，因為瀏覽器維度不包含瀏覽器導覽區或邊界。

## 將資料填入此維度中

從瀏覽器的`screen.width`和`screen.height`屬性自動在使用者端收集監視器解析度。 可直接用於任何AppMeasurement或Web SDK （標籤）實作，且沒有變數可供設定。 如果您在AppMeasurement或網頁SDK之外（例如透過API）收集資料，請在影像要求中傳送值。 如果資料收集程式庫遺失或無法收集監視器解析度，該資料會列在[!UICONTROL `Not Specified`]下。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（自動收集） |
| **網頁SDK / XDM欄位** | 無（自動收集） |
| **查詢引數** | [`s`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<resolution>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **位元組限制** | 20位元組 |
| **持續性** | 不適用 |

## 維度項目

維度項目包含所有收集的螢幕解析度。 範例值包括 `1920 x 1080`、`1366 x 768` 和 `1280 x 720`。
