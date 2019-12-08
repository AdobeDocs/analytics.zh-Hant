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



# homepage

此變數在 Internet Explorer 中會指出目前的頁面是否設為使用者的首頁。


<!-- 

homepage.xml

 -->

此變數會在頁面程式碼執行後、*`doPlugins`* 執行前填入。

> [!NOTE]此變數僅供讀取，絕不可設定。

您可以讀取這些值，並將其複製到 prop/eVar 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

| 查詢參數 | 值 | 範例 | 受影響的報表 |
|---|---|---|---|
| hp | Y 或 N | Y | 流量 &gt; 技術 &gt; 首頁 |
