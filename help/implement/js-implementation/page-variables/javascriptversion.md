---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---



# javascriptVersion

 變數會指出瀏覽器支援的 JavaScript 版本。


<!-- 

javascriptVersion.xml

 -->

此變數會在頁面程式碼執行後、*`doPlugins`* 執行前填入。

> [!NOTE]此變數僅供讀取，絕不可設定。

您可以讀取這些值，並將其複製到 prop/eVar 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 | 受影響的報表 |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | 流量 &gt; 技術 &gt; JavaScript 版本 |

JavaScript 檔案的 H.10 版和更高版本可正確偵測到 1.7 版 (H.10 發行時的最高版本)。舊版的 JavaScript 檔案版本最高只能偵測到 1.3 版
