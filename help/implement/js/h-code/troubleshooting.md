---
title: 疑難排解 H 程式碼實施
description: 瞭解舊版 JavaScript 實施的一些常見問題。
feature: Implementation Basics
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
role: Developer
TQID: https://experienceleague.adobe.com/DootwtTj5kDIRHKhFPeY3Fnt3bWdVLsXc6J3UEc5LPI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 100%

---

# 疑難排解 H 程式碼實施

以下是 H 程式碼實施專用的疑難排解步驟。

## 將 Analytics 程式碼放入 head 標記中

>[!NOTE]
>
>雖然 H 程式碼實作需要在 `<body>` 標記中參照的程式碼，但有其他實作 (例如使用 Adobe Experience Platform 中的標記) 需要在 `<head>` 標記中參照的程式碼。

Analytics 程式碼會建立不可見的 1x1 像素影像。 以前，常見的實施做法是將 `s_code.js` 參考放在 `<head>` 標記中。 將程式碼放在這裡，可避免影像以任何方式影響頁面配置。 這樣還可以及早執行代碼，讓您更有效地計算部分頁面載入的頁面瀏覽數。

然而，某些程式碼元素必須要有 `<body>` 物件存在。 如果 Analytics JavaScript 程式碼位於 `<head>` 標記中，則會在 `<body>` 物件存在前先行執行。 因此，您的實施將不會收集 [!UICONTROL ClickMap] 資料、檔案下載或退出連結的自動追蹤，抑或是連線類型資料。 將 `s_code.js` 的指令碼參考放入 `<head>` 標記中是個可行的做法，不過只有在少數的 Analytics 版本中能發揮作用。

Analytics 程式碼碼可在正常格式的 HTML 頁面中，放置於 `<body>` 標記內的任一處。 Adobe 建議盡可能將 Analytics 程式碼放在 `<body>` 標記頂端的鄰近位置。 請確認所有頁面變數會在 `s_code.js` 檔案載入後設定。

>[!TIP]
>
>若您想整合 Adobe Analytics 與 Target，則必須將 JavaScript 包含檔案放在頁面底部。
