---
description: 相關範例，內含透過一般客戶互動而傳送的伺服器呼叫樣本。
keywords: Analytics 實施
seo-description: 相關範例，內含透過一般客戶互動而傳送的伺服器呼叫樣本。
seo-title: 範例瀏覽
solution: Analytics
subtopic: 訪客
title: 範例瀏覽
topic: 開發人員和實施
uuid: bc5f8f56-52e3-42d8-af1 a-7f5 c7 b9496 c0
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 範例瀏覽

>[!IMPORTANT]
>
>不再建議這種識別跨裝置訪客的方法。Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

相關範例，內含透過一般客戶互動而傳送的伺服器呼叫樣本。

| 伺服器呼叫 | 動作 | 訪客 ID Cookie | 訪客 ID 變數 | 有效訪客 ID | 瀏覽頁碼 | 瀏覽次數 |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | 一名訪客點按了行銷電子郵件中的連結，從家用電腦瀏覽您的網站。這名訪客在此之前曾瀏覽您的網站 7 次。 | 1 | - | 1 | 1 | 8 |
| 2-8 | 瀏覽您網站上的另 7 個頁面。 | 1 | - | 1 | 2-8 | 8 |
| 9 | 對家用電腦進行驗證。 | 1 | CID1 | CID1 | 9 <br>This is CID1&#39;s first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1.</br> | 8 |
| 10 | 瀏覽另 1 個頁面。 | 1 | CID1 | CID1 | 10 | 8 |
| 11 | 在辦公室以筆記型電腦開啟網站。這位訪客以前未曾使用此裝置瀏覽您的網站。 | 2 | - | 2 | 1 | 1 |
| 12 | 對筆記型電腦進行驗證。 | 2 | CID1 | CID1 | 1 | 9 |
| 13 | 檢視另 1 個頁面。 | 2 | CID1 | CID1 | 2 | 9 |