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


# trackingServer

 變數會用於第一方 Cookie 實施，以指定影像要求和 Cookie 寫入所在的網域。


<!-- 

trackingServer.xml

 -->

用於非安全頁面。若&#x200B;*`trackingServer`*&#x200B;已定義，則不會傳送任何資料到 2o7.net。若未定義 *`trackingServer`* (且未定義 dc)，則會將資料送往 112.2o7.net。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | "" |

[此處](https://helpx.adobe.com/analytics/kb/determining-data-center.html)提供 Adobe 資料中心清單。