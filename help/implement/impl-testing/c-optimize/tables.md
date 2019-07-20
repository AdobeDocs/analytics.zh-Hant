---
description: 有許多網頁瀏覽器必須在完成整個表格的編譯後，才會開始顯示表格內容。
keywords: Analytics 實施
seo-description: 有許多網頁瀏覽器必須在完成整個表格的編譯後，才會開始顯示表格內容。
seo-title: 表格
solution: Analytics
subtopic: 疑難排解
title: 表格
topic: 開發人員和實施
uuid: f72d7894-38bd-4926-bce4-0c6 af7278 c63
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# 表格

有許多網頁瀏覽器必須在完成整個表格的編譯後，才會開始顯示表格內容。

若頁面的完整內容位於一個大表格中，瀏覽器就必須先編譯頁面的完整內容，才能加以顯示。

對位於表格標記以外的 JavaScript 程式庫檔案發出呼叫，可確保對 Analytics 伺服器的呼叫不會影響到頁面內容的顯示。

>[!NOTE]
>
>檔案應放置在影像的合法位置，且必須在 <body> tag and the close </body> tag.

