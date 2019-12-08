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


# colorDepth

 變數可用來顯示畫面的每個像素上用以顯示顏色的位元數。


<!-- 

colordepth.xml

 -->

例如，32 代表畫面使用 32 位元的顏色。此變數會在頁面程式碼執行後、*`doPlugins`* 執行前填入。

> [!NOTE]此變數僅供讀取，絕不可設定。

您可以讀取這些值，並將其複製到 `props/eVars` 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 | 受影響的報表 |
|---|---|---|---|
| c | 8、16 和 32 | 32 | 流量 &gt; 技術 &gt; 螢幕色彩深度 |
