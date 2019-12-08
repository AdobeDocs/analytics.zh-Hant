---
description: 將 JavaScript 程式庫檔案的呼叫放置於頁面頂端，可確保影像會是最先下載的元素之一。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: JavaScript 檔案的位置和並行性
topic: Developer and implementation
uuid: ed5118a8-b142-4fab-8aa1-92d931cc1439
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# JavaScript 檔案的位置和並行性

將 JavaScript 程式庫檔案的呼叫放置於頁面頂端，可確保影像會是最先下載的元素之一。

大部分的網頁瀏覽器都會以並行方式下載影像。一般情況下，會同時下載三到四個影像。

由於大部分的網頁瀏覽器都會以並行方式下載元素，因此有許多常用瀏覽器 (包括 Internet Explorer) 的狀態列都不會正確反映瀏覽器正嘗試載入的元素。例如，您的狀態列可能指出瀏覽器正在等待影像 1 進行下載。網路封包測試顯示您的瀏覽器已接收到影像 1，而正在等待影像 2。

> [!NOTE]由於第三方網際網路效能稽核提供者 (例如 Keynote Systems) 會以循序方式下載頁面影像元素，而非並行方式，因此會不同於一般的使用者經驗。

