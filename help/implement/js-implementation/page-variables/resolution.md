---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# 解析度

此變數會指出檢視網頁之訪客的螢幕解析度。


<!-- 

resolution.xml

 -->

此變數會在頁面程式碼執行後、*`doPlugins`* 執行前填入。

> [!NOTE]此變數僅供讀取，絕不可設定。

您可以讀取這些值，並將其複製到 prop/eVar 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 | 受影響的報表 |
|---|---|---|---|
| s | WxH | 1680 x 1050 | 流量 &gt; 技術 &gt; 螢幕解析度 |

