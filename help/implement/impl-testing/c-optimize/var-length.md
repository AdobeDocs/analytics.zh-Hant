---
description: Analytics 變數的長度可能會影響到 HTML 程式碼片段、JavaScript 程式庫檔案和影像要求的大小。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: 變數長度
topic: Developer and implementation
uuid: 87deabb3-2acb-4797-9a65-769d9e2fbd62
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 變數長度

Analytics 變數的長度可能會影響到 HTML 程式碼片段、JavaScript 程式庫檔案和影像要求的大小。

若客戶有許多較長的變數 (60 個字元或更多)，其值可能會取代為較短的識別碼。資料分類或 VISTA 規則可用來將識別碼轉譯為好記名稱。

> [!NOTE]大部分的 Analytics 變數長度上限為 100 個字元 (eVar 的上限為 255 個字元)。Internet Explorer 允許 GET 影像要求 URL 中最多總共可有 2,048 個字元。影像要求限制不僅適用於變數，也適用於瀏覽器、作業系統和瀏覽器外掛程式 (僅限 Netscape/Mozilla) 的相關資訊。

