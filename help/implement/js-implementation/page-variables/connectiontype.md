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




# connectionType

 變數在 Internet Explorer 中會指出瀏覽器是設定於 LAN 還是數據機連線。


<!-- 

conntype.xml

 -->

此變數會在頁面程式碼執行後、*`doPlugins`* 執行前填入。

> [!NOTE]此變數僅供讀取，絕不可設定。

您可以讀取這些值，並將其複製到 `props/eVars` 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 | 受影響的報表 |
|---|---|---|---|
| ct | LAN 或數據機 | LAN | 流量 &gt; 技術 &gt; 連線類型 |
