---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 0c7093518933a88c5057ba95cb3564d6ca0ebcad

---



# s.forcedLinkTrackingTimeout

此值表示等待時間上限。Specifically, it sets the maximum number of milliseconds to wait for tracking to finish before performing the `doneAction` that was passed into `s.tl`. 若追蹤連結呼叫在此逾時前完成，就會立即執行 `doneAction`。若您注意到追蹤連結呼叫未完成，您可能需要提高此逾時。

預設值= 250

範例: `s.forcedLinkTrackingTimeout = 500`
