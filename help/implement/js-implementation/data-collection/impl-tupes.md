---
description: 這項資訊適用於報告與實施皆熟稔的進階使用者。若不瞭解後果，請勿嘗試編輯您的實施。如需進行實施變更，請與組織的客戶經理連絡。
keywords: Analytics 實作
seo-description: 這項資訊適用於報告與實施皆熟稔的進階使用者。若不瞭解後果，請勿嘗試編輯您的實施。如需進行實施變更，請與組織的客戶經理連絡。
seo-title: 追蹤不同的實作類型
solution: Analytics
title: 追蹤不同的實作類型
topic: 開發人員和實作
uuid: a0a3229a-79a2-4dc2-b0be-4b8fac2efa3a
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 追蹤不同的實作類型

這項資訊適用於報告與實施皆熟稔的進階使用者。若不瞭解後果，請勿嘗試編輯您的實施。如需進行實施變更，請與組織的客戶經理連絡。

若您使用多種類型的實施 (例如 JavaScript 與硬式編碼影像要求)，請確定下列變數均已指定並彼此相符: 

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (若使用 SSL)

若各個實施間的這些變數不相符，可能會將使用者視為個別訪客來追蹤。
