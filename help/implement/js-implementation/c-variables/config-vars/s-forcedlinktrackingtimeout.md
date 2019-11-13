---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---



# s.forcedLinkTrackingTimeout

在執行已傳入 的 `s.tl`doneAction 之前，等待追蹤完成的毫秒數上限。此值表示等待時間上限。若追蹤連結呼叫在此逾時前完成，就會立即執行 doneAction。若您注意到追蹤連結呼叫未完成，您可能需要提高此逾時。

預設值= 250

範例: `s.forcedLinkTrackingTimeout = 500`
