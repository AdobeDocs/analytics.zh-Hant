---
title: 瀏覽器高度 - 分段
description: 瀏覽器視窗的高度 (像素)。
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
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
source-wordcount: '318'
ht-degree: 40%
---
# 瀏覽器高度

「瀏覽器高度 — 分段」[維度](overview.md)會顯示瀏覽器視窗的高度，並將其分類為預先定義的群組。 如果您想要瞭解訪客在您網站上的「折頁」位置，此維度就十分實用。 瞭解折頁的位置可讓您將內容最佳化以供檢視。

此維度與熒幕高度不同。 瀏覽器高度是可檢視瀏覽器空間內的像素數，而螢幕高度則是整個監視器的高度 (像素)。 如果您想在自己的電腦上觀察這兩個變數之間的差異，請開啟瀏覽器主控台 (在大部分的瀏覽器上為 F12)，並將下列程式碼複製並貼到主控台中：

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

瀏覽器高度通常會小於或等於熒幕高度，因為瀏覽器高度不包含瀏覽器導覽區或邊界。

>[!NOTE]
>
>Data Warehouse也提供&#39;[!UICONTROL 瀏覽器高度 — 精細]&#39;維度，此維度會報告精確的畫素高度，而非將值分組到預先定義的值區。

## 將資料填入此維度中

系統會自動從瀏覽器的`window.innerHeight`屬性在使用者端收集瀏覽器高度。 可直接用於任何AppMeasurement或Web SDK （標籤）實作，且沒有變數可供設定。 如果您在AppMeasurement或網頁SDK之外（例如透過API）收集資料，請在每次造訪的第一次點選時傳送值。 如果瀏覽器高度在造訪期間有所調整，將不會記錄該調整。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（自動收集） |
| **網頁SDK / XDM欄位** | 無（自動收集） |
| **查詢引數** | [`bh`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<browserHeight>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **值範圍** | 0-65,535 |
| **持續性** | 造訪 |

## 維度項目

Dimension專案包含所有收集到的瀏覽器高度，並歸類到預先定義的群組中。 例如，如果點擊的瀏覽器高度為 `720`，則會將其歸類到維度項目 `700 to 799` 中。
