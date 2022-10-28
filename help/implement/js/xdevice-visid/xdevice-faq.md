---
title: 跨裝置訪客身份識別常見問答
description: 跨裝置訪客身份識別的常見問題
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 81%

---

# 跨裝置訪客身份識別常見問答

跨裝置訪客身份識別的常見問題。

+++跨裝置訪客身分識別與跨裝置分析之間有何差異？
跨裝置訪客身份識別使用 `visitorID` 變數將裝置繫結在一起，但有幾項主要限制。此識別方法的最大限制之一，就是除非已識別裝置，否則會隔離未驗證的點擊。這些未驗證的點擊可能會誇大您的不重複訪客計數。

跨裝置分析是 Adobe 最新的跨裝置訪客身份識別方法。它使用 Experience Cloud ID Service和裝置圖表，以回溯方式將不同裝置的造訪拼接在一起。CDA 需要使用 `setCustomerIDs` 函數來判斷同一訪客使用的裝置。
+++

+++跨裝置訪客身分識別如何處理區段？
跨裝置訪客身份識別處理區段的方式與其他功能類似。它會分別審視每個點擊，確認點擊是否符合區段標準，並將這些符合的點擊納入您的資料中。使用造訪和訪客型容器的區段仍會審視訪客 ID。請確定您的實作使用 `visitorID` 變數，以便一致地識別分段的不重複訪客。
+++
