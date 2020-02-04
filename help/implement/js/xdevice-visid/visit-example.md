---
description: 相關範例，內含透過一般客戶互動而傳送的伺服器呼叫樣本。
keywords: Analytics Implementation
subtopic: Visitors
title: 跨裝置訪客身分識別範例
topic: Developer and implementation
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
translation-type: tm+mt
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# 跨裝置訪客身分識別範例

> [!IMPORTANT]不建議您繼續使用這種跨裝置識別訪客的方法。請參 [閱「元件」使用指南](/help/components/cda/cda-home.md) 中的「跨裝置分析」。

下列範例說明跨裝置訪客識別如何使用在共同客戶互動中傳送的伺服器呼叫範例來運作。

| 伺服器呼叫 | 動作 | 訪客 ID Cookie | 訪客 ID 變數 | 有效訪客 ID | 瀏覽頁碼 | 訪問次數 |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | 一名訪客點按了行銷電子郵件中的連結，從家用電腦瀏覽您的網站。這名訪客在此之前曾瀏覽您的網站 7 次。 | 1 | - | 1 | 1 | 8 |
| 2-8 | 瀏覽您網站上的另 7 個頁面。 | 1 | - | 1 | 2-8 | 8 |
| 9 | 對家用電腦進行驗證。 | 1 | CID1 | CID1 | 9 <br>(This is CID1&#39;s first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1.) | 8 |
| 10 | 瀏覽另 1 個頁面。 | 1 | CID1 | CID1 | 10 | 8 |
| 11 | 在辦公室以筆記型電腦開啟網站。這位訪客以前未曾使用此裝置瀏覽您的網站。 | 2 | - | 2 | 1 | 1 |
| 12 | 對筆記型電腦進行驗證。 | 2 | CID1 | CID1 | 1 | 9 |
| 13 | 檢視另 1 個頁面。 | 2 | CID1 | CID1 | 2 | 9 |

## 瀏覽計數

Analytics會在每次看到點擊時計算一次瀏覽，其瀏覽頁數等於1。

使用上表，新瀏覽被計為4次：點擊1、9、11和12。

## 訪客計數

Analytics 會將每個唯一的有效訪客 ID 計為獨特訪客。

使用上表，新訪客被計為3次：點擊1、9和10。

當您使用跨裝置訪客身分識別時，您看到的獨特訪客數目可能會增加。 同一次瀏覽可對訪客計數兩次：一次，以進行初始瀏覽，並在使用者經過驗證後再次進行。

![](assets/visitors.png)

初次關聯後，瀏覽計數會恢復正常，因為訪客是透過其瀏覽器Cookie來關聯。 若訪客稍後檢視了您的網站，然後進行驗證，訪客計數並不會不實膨脹，因為有效訪客 ID 在驗證之後並未變更。

![](assets/visitors_2.png)

在識別獨特訪客時，請務必盡可能保持一致。 例如，在使用者經過驗 `visitorID` 證時，請一律使用變數。
