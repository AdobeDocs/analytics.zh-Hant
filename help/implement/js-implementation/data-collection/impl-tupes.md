---
description: 這項資訊適用於報告與實施皆熟稔的進階使用者。若不瞭解後果，請勿嘗試編輯您的實施。如需進行實施變更，請與組織的客戶經理連絡。
keywords: Analytics Implementation
title: 追蹤不同的實作類型
topic: Developer and implementation
uuid: a0a3229a-79a2-4dc2-b0be-4b8fac2efa3a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 追蹤不同的實作類型

這項資訊適用於報告與實施皆熟稔的進階使用者。若不瞭解後果，請勿嘗試編輯您的實施。如需進行實施變更，請與組織的客戶經理連絡。

若您使用多種類型的實施 (例如 JavaScript 與硬式編碼影像要求)，請確定下列變數均已指定並彼此相符: 

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (若使用 SSL)

若各個實施間的這些變數不相符，可能會將使用者視為個別訪客來追蹤。
