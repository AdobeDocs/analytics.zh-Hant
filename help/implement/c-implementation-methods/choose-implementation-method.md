---
description: 有多種方式可實施 Adobe Analytics。
keywords: Analytics實作；實施方法；動態標籤管理；dtm；javascript
seo-description: 有多種方式可實施 Adobe Analytics。
seo-title: 選擇實施方法
solution: Analytics
title: 選擇實施方法
topic: 開發人員和實施
uuid: 20d3317f-7c63-4421-93e0-fff60 dbd9 f87
translation-type: tm+mt
source-git-commit: b1e69abd65f171b804e7f56031e594890bbd27bb

---


# 選擇實施方法

有多種方式可實施 Adobe Analytics。

* [!UICONTROL Adobe Experience Platform Launch] (建議)
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Adobe Experience Platform Launch]{#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL Experience Platform Launch] 是Adobe新一代的網站標籤和行動SDK管理功能。[!UICONTROL Experience Platform Launch] 提供您簡單的方式，來部署和管理所有必要的分析、行銷和廣告整合，以提供強大的客戶體驗。

[!UICONTROL Experience Platform Launch] 可讓任何人建立並維護自己的整合，稱為 [!DNL Experience Platform Launch]擴充功能。These extensions are available to web and mobile [!UICONTROL Experience Platform Launch] customers in an app-store experience, so customers can quickly install, configure, and deploy their integrations.

For more information, see [Getting Started with Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL 動態標籤管理] 會自動化實施所需的詳細資料工作 [!DNL Analytics]。Enter the required information in a form-based interface, and [!DNL Dynamic Tag Management] generates the code you need to add to your pages.
對JavaScript熟悉，並瞭解基本Analytics術語，例如

* [eVar](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) 是什麼及其運作方式
* 何時使用 [自訂事件](../../implement/analytics-terminology-basics/c-props-evars/event-custom.md#concept_CDA3C98C85B24A71B4B5C71F24BF918F)

如需有關存取動態標籤管理與執行的資訊，請參閱動態標籤管理產品文件的[快速入門](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html)。

如需詳細資訊，請參閱[使用動態標籤管理實施Analytics](../../implement/c-implement-with-dtm/dtm-implementation-overview.md)。

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

JavaScript 實施方法需要您手動在頁面上設定 JavaScript 程式碼。如果您使用Experience Platform Launch或「動態標籤管理」實施方法，就可以簡化這項工作。不過，部分使用者可能需要 JavaScript 方法。

JavaScript 實施需要:

* 高強的 JavaScript 技能
* 對 Analytics 概念與術語有深厚瞭解

如需詳細資訊，請參閱[使用JavaScript實施Analytics](../../implement/js-implementation/javascript-implementation-overview.md)。
