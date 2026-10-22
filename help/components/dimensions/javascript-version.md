---
title: JavaScript版本
description: 訪客瀏覽器支援的JavaScript版本。
feature: Dimensions
source-git-commit: a68e13c9232ef8d975fd1256168a0addf677f5ac
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 10%
---
# JavaScript版本

「JavaScript版本」[維度](overview.md)會報告訪客瀏覽器支援的JavaScript版本。 不會回報AppMeasurement程式庫的版本。

>[!IMPORTANT]
>
>此維度僅在 Data Warehouse 中可用。 如果您想要在其他Analytics解決方案中使用JavaScript版本，請考慮在每次點選時將值複製到[eVar](evar.md)。

## 將資料填入此維度中

AppMeasurement會自動在瀏覽器中偵測JavaScript功能，並傳送`j`查詢字串引數中的版本值。 沒有可設定的實作變數。 這項偵測使用舊版JavaScript版本標籤，並非現代ECMAScript功能支援的完整衡量標準。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（自動收集） |
| **網頁SDK / XDM欄位** | [`environment.browserDetails.javaScriptVersion`](/help/implement/aep-edge/xdm-var-mapping.md) |
| **查詢引數** | [`j`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<javaScriptVersion>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **大量資料插入API資料行** | [`javaScriptVersion`](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/column-reference) |
| **位元組限制** | 5位元組 |
| **持續性** | 點擊 |

## 維度項目

Dimension專案包含從訪客的瀏覽器（例如`1.5`和`1.6`）收集的JavaScript版本值。
