---
description: 'null'
keywords: Analytics 實施
seo-description: 'null'
seo-title: 實作Adobe退出
solution: Analytics
title: 實作Adobe退出
topic: 開發人員和實施
uuid: fc3a411c-8476-409d-99de-05b34ab
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 實作Adobe退出

有些來到您網站的訪客，可能不希望其瀏覽資訊被 Adobe Experience Cloud 產品和服務加以彙集與分析，或用於提供相關的內容與廣告。Adobe 提供方法，可讓您提供來到您網站的訪客選擇退出，不讓下列 Adobe 產品收集其資訊:

* Adobe Analytics
* Adobe Target
* Adobe Audience Targeted Creative
* Adobe AudienceManager
* Adobe AdLens
* Adobe Experience Manager

## 隱私權原則建議 {#section_BBDEE21C259842F7881642E31FB3D9B7}

Adobe 建議您提供關於選擇退出不讓 Adobe 產品或服務收集其瀏覽資訊的容易找到且容易了解的相關資訊給網站訪客。

訪客可以在 [Adobe 隱私中心](https://www.adobe.com/privacy.html)了解更多關於 Adobe 一般如何將其收集到的資訊用於提供產品和服務的詳細資訊。不過，由於您完全掌控如何在您的網站上實施我們的服務，所以由您決定如何向網站訪客說明他們使用我們產品和服務的方式。您需負責建立自己的隱私權原則、遵循您的隱私權原則、遵循您與 Adobe 簽署的服務協定，以及遵循所有適用法律。

## Opt-outs for Adobe Analytics (including Reports &amp; Analytics, Data Warehouse, Ad Hoc Analysis) {#section_8089B80CDA4043C9BC2DED49E484E8D7}

Adobe offers three types of opt-outs for Adobe Analytics (including [!UICONTROL Reports &amp; Analytics], [!UICONTROL Data Warehouse], [!UICONTROL Ad Hoc Analysis]):

* If you implement Adobe Analytics products with your own first-party cookie, you need to [develop your own customized opt-out link](../../../implement/js-implementation/data-collection/opt-out-link.md#concept_C2C4F19811A445EF9E9BEAC709B568A9) for your website visitors.
* Adobe 也公開提供退出機制給使用 Adobe 2o7.net 和 omtrdc.net 網域之 Cookie 集的網站使用。您可從 [Adobe 隱私中心](https://www.adobe.com/privacy/opt-out.html)存取此退出機制。
* 您的客戶可以選擇使用瀏覽器的 Cookie 設定啟用退出。請參閱[啟用瀏覽器 Cookie 的隱私權設定](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/?f=browser_cookie_settings)。

無論選擇哪種退出機制，Adobe 都建議您在隱私權原則中 (或在法律要求或根據目前最佳實務建議的位置) 清楚說明可使用的退出機制。
