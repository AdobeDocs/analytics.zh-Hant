---
title: 疑難排解H程式碼實作
description: 瞭解舊版JavaScript實作的一些常見問題。
translation-type: tm+mt
source-git-commit: 69138bdedb42b66449426fee39822520ee4b1198

---


# 疑難排解H程式碼實作

以下是H程式碼實作的疑難排解步驟。

## 將 Analytics 程式碼放入 head 標記中

> [!NOTE] 雖然H程式碼實作需要在標籤中引用程式碼， `<body>` 但其他實作（例如使用Adobe Experience Platform Launch）則需要在標籤中引用程 `<head>` 式碼。

Analytics程式碼會建立不可見的1x1像素影像。 以前，常見的實作做法是將參考 `s_code.js` 放在標籤中 `<head>` 。 將程式碼放在此處，可避免影像以任何方式影響頁面配置。 此外，它的執行速度也更快，可讓您更有效率地計算部分頁面載入的頁面檢視次數。

However, certain elements of the code require the existence of the `<body>` object. 如果Analytics JavaScript程式碼位於標籤中， `<head>` 則會在物件存在前執 `<body>` 行它。 As a result, your implementation does not collect [!UICONTROL ClickMap] data, automatic tracking of file downloads or exit links, or connection type data. 將指令碼參考放 `s_code.js` 入標 `<head>` 記中有用，但結果是Analytics版本非常有限。

The Analytics code can be placed anywhere inside the `<body>` tag of a well-formed HTML page. Adobe建議將Analytics程式碼盡量放在離標籤最 `<body>` 近的位置。 請確定在檔案載入後已設定任 `s_code.js` 何頁面變數。

> [!TIP] 如果您想要將Adobe Analytics與Adobe Target整合，JavaScript包含檔案必須放在頁面底部。
