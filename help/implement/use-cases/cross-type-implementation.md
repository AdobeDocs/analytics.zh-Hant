---
title: 追蹤不同的實施類型
description: 使用不同的實施類型，順暢地在不同的實施間追蹤訪客。
feature: Implementation Basics
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 100%

---

# 追蹤不同的實施類型

這項資訊適用於報告與實施皆熟稔的進階使用者。若不瞭解後果，請勿嘗試編輯您的實施。如需進行實施變更，請與組織的客戶經理連絡。

若您使用多種類型的實施 (例如 JavaScript 與硬式編碼影像要求)，請確定下列變數均已指定並彼此相符：

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (若使用 SSL)

若各個實施間的這些變數不相符，可能會將使用者視為個別訪客來追蹤。
