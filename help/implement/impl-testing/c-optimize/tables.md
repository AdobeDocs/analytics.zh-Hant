---
description: 有許多網頁瀏覽器必須在完成整個表格的編譯後，才會開始顯示表格內容。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: 表格
topic: Developer and implementation
uuid: f72d7894-38bd-4926-bce4-0c6af7278c63
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 表格

有許多網頁瀏覽器必須在完成整個表格的編譯後，才會開始顯示表格內容。

若頁面的完整內容位於一個大表格中，瀏覽器就必須先編譯頁面的完整內容，才能加以顯示。

對位於表格標記以外的 JavaScript 程式庫檔案發出呼叫，可確保對 Analytics 伺服器的呼叫不會影響到頁面內容的顯示。

> [!NOTE] 檔案應放置在合法的影像位置，且必須顯示在開頭 <body> 標籤與結尾 </body> 標籤之間。

