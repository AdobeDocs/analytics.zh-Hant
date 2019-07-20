---
title: SSL 憑證授權
seo-title: Adobe Analytics SSL憑證授權
description: null
seo-description: null
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# SSL 憑證授權

如果您使用第一方 Cookie 並且測量安全流量，則必須提供足夠支援 RDC 實施的 SSL 憑證授權。

您的 SSL 憑證授權必須能支援安裝高達 10 部伺服器。這些憑證安裝在遍佈全球的負載平衡器上。隨著 Adobe 將更多資料收集中心上線，SSL 憑證也需要變更。此項變更隨時間對您憑證授權需求的影響，視您擁有的憑證授權類型而定:

* 伺服器型授權: RDC 部署的授權需求會隨時間成長。
* 容量型授權: 授權需求不受基礎結構變更影響，但會受隨時間的流量容量變更影響。
* 不限數目的授權: 授權需求應隨時間而維持相對穩定。

如果您要自行提供憑證，則您需自行負責購買和維護該憑證。請檢查憑證供應商的合約，確認可將 SSL 憑證安裝在多個資料中心。

或者，Adobe 可以透過 [Adobe Managed Certificate Program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html)，免費替您管理憑證。
