---
title: 跨裝置訪客身份識別常見問題集
description: 跨裝置訪客身份識別的常見問題
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
role: Developer
TQID: https://experienceleague.adobe.com/h3kyR8lnSdl5rQKj9kmVXBt6rspjsALfUUaEh2-cAhM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 80%

---

# 跨裝置訪客身份識別常見問題集

跨裝置訪客身份識別的常見問題。

+++跨裝置訪客身分識別與跨裝置分析之間有何差異？
跨裝置訪客身份識別使用 `visitorID` 變數將裝置繫結在一起，但有幾項主要限制。 此識別方法的最大限制之一，就是除非已識別裝置，否則會隔離未驗證的點擊。 這些未驗證的點擊可能會誇大您的不重複訪客計數。

跨裝置分析是 Adobe 最新的跨裝置訪客身份識別方法。 它使用Experience Cloud ID服務和欄位式拚接，以回溯方式將不同裝置的造訪拼接在一起。 CDA 需要使用 `setCustomerIDs` 函數來判斷同一訪客使用的裝置。
+++

+++跨裝置訪客身份識別如何處理區段？
跨裝置訪客身份識別處理區段的方式與其他功能類似。 它會分別審視每個點擊，確認點擊是否符合區段標準，並將這些符合的點擊納入您的資料中。 使用造訪和訪客型容器的區段仍會審視訪客 ID。 請務必讓您的實作盡可能使用 `visitorID` 變數，以便一致地識別分段的不重複訪客。
+++
