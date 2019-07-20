---
description: Akamai 和 Speedera 之類的內容遞送服務或內容分送網路 (CDN) 可將網頁內容發送至更接近網路邊緣之處，讓經常受到要求的文件能夠保持在其受到存取的位置附近。
keywords: Analytics 實施
seo-description: Akamai 和 Speedera 之類的內容遞送服務或內容分送網路 (CDN) 可將網頁內容發送至更接近網路邊緣之處，讓經常受到要求的文件能夠保持在其受到存取的位置附近。
seo-title: 內容遞送服務/網路
solution: Analytics
subtopic: 疑難排解
title: 內容遞送服務/網路
topic: 開發人員和實施
uuid: 6cb57c59-d0 f9-4ca5-9f15-0e74 e585 a4 a
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# 內容遞送服務/網路

Akamai 和 Speedera 之類的內容遞送服務或內容分送網路 (CDN) 可將網頁內容發送至更接近網路邊緣之處，讓經常受到要求的文件能夠保持在其受到存取的位置附近。

一般而言，這可以降低存取延遲性、頻寬使用量和基礎結構成本。

「JavaScript 適用的 AppMeasurement」的程式庫檔案可透過 CDN 來遞送，以提升效能以及將檔案遞送給網站訪客的效率。Adobe 客戶必須確定他們已正確設定其 CDN 服務。CDN 是下載時間波動的常見原因之一，且在下載時間出現任何變動時，應將 CDN 視為最可能的成因。

標記管理器會將所有 JavaScript 儲存在 CDN 上。
