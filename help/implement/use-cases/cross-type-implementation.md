---
title: 追蹤不同的實施類型
description: 使用不同的實施類型，順暢地在不同的實施間追蹤訪客。
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# 追蹤不同的實施類型

這項資訊適用於報告與實施皆熟稔的進階使用者。若不瞭解後果，請勿嘗試編輯您的實施。如需進行實施變更，請與組織的客戶經理連絡。

若您使用多種類型的實施 (例如 JavaScript 與硬式編碼影像要求)，請確定下列變數均已指定並彼此相符：

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (若使用 SSL)

若各個實施間的這些變數不相符，可能會將使用者視為個別訪客來追蹤。
