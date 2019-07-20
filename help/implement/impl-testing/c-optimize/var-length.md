---
description: Analytics 變數的長度可能會影響到 HTML 程式碼片段、JavaScript 程式庫檔案和影像要求的大小。
keywords: Analytics 實施
seo-description: Analytics 變數的長度可能會影響到 HTML 程式碼片段、JavaScript 程式庫檔案和影像要求的大小。
seo-title: 變數長度
solution: Analytics
subtopic: 疑難排解
title: 變數長度
topic: 開發人員和實施
uuid: 87deabb3-2acb-4797-9a65-769d9e2fbd62
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# 變數長度

Analytics 變數的長度可能會影響到 HTML 程式碼片段、JavaScript 程式庫檔案和影像要求的大小。

若客戶有許多較長的變數 (60 個字元或更多)，其值可能會取代為較短的識別碼。資料分類或 VISTA 規則可用來將識別碼轉譯為好記名稱。

>[!NOTE]
>
>大部分的Analytics變數最多有100個字元(eVar最多可有255個字元)。Internet Explorer 允許 GET 影像要求 URL 中最多總共可有 2,048 個字元。影像要求限制不僅適用於變數，也適用於瀏覽器、作業系統和瀏覽器外掛程式 (僅限 Netscape/Mozilla) 的相關資訊。

