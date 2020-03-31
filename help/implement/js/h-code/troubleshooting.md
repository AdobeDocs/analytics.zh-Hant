---
title: 疑難排解 H 程式碼實施
description: 瞭解舊版 JavaScript 實施的一些常見問題。
translation-type: ht
source-git-commit: 69138bdedb42b66449426fee39822520ee4b1198

---


# 疑難排解 H 程式碼實施

以下是 H 程式碼實施專用的疑難排解步驟。

## 將 Analytics 程式碼放入 head 標記中

> [!NOTE] H 程式碼實施需要在 `<body>` 標記中參考程式碼，其他實施 (例如使用 Adobe Experience Platform Launch) 則需要在 `<head>` 標記中參考程式碼。

Analytics 程式碼會建立不可見的 1x1 像素影像。以前，常見的實施做法是將 `s_code.js` 參考放在 `<head>` 標記中。將程式碼放在這裡，可避免影像以任何方式影響頁面配置。這樣還可以及早執行代碼，讓您更有效地計算部分頁面載入的頁面檢視數。

然而，某些程式碼元素必須要有 `<body>` 物件存在。如果 Analytics JavaScript 程式碼位於 `<head>` 標記中，則會在 `<body>` 物件存在前先行執行。因此，您的實施將不會收集 [!UICONTROL ClickMap] 資料、檔案下載或退出連結的自動追蹤，抑或是連線類型資料。將 `s_code.js` 的指令碼參考放入 `<head>` 標記中是個可行的做法，不過只有在少數的 Analytics 版本中能發揮作用。

Analytics 程式碼碼可在正常格式的 HTML 頁面中，放置於 `<body>` 標記內的任一處。Adobe 建議盡可能將 Analytics 程式碼放在 `<body>` 標記頂端的鄰近位置。請確認所有頁面變數會在 `s_code.js` 檔案載入後設定。

> [!TIP] 若您想整合 Adobe Analytics 與 Target，則必須將 JavaScript 含入檔放在頁面底部。
