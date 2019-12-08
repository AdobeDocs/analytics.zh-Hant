---
description: 有多種方式可實施 Adobe Analytics。
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;javascript
title: 選擇實作方法
topic: Developer and implementation
uuid: 20d3317f-7c63-4421-93e0-fff60dbd9f87
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 選擇實作方法

有多種方式可實施 Adobe Analytics。

* [!UICONTROL Adobe Experience Platform Launch] (建議使用)
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Adobe Experience Platform Launch] {#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL Experience Platform Launch] 是 Adobe 推出的下一代網頁標籤與行動 SDK 管理功能。[!UICONTROL Experience Platform Launch] 可讓您透過簡單的方式部署及管理所有必要的分析、行銷及廣告整合功能，以便支援相關客戶體驗。

[!UICONTROL Experience Platform Launch] 可供任何使用者建置和維護自己本身與 [!DNL Experience Platform Launch] 的整合 (也稱為擴充功能)。這些擴充功能可為使用網頁版和行動版的  [!UICONTROL Experience Platform Launch] 客戶提供應用程式商店的使用體驗，讓客戶能快速安裝、設定和部署自己的整合。

For more information, see [Getting Started with Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL Dynamic Tag Management] 會自動執行實作 [!DNL Analytics] 所需的大部分瑣碎工作。在表單式介面中輸入必填資訊，[!DNL Dynamic Tag Management] 便會產生所需的程式碼，以新增至頁面。熟悉 JavaScript 以及瞭解 Analytics 基本術語會很有幫助，例如

* [eVar](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) 是什麼及其運作方式
* [自訂事件](/help/implement/analytics-terminology-basics/c-props-evars/event-custom.md)的使用時機

如需有關存取動態標籤管理與執行的資訊，請參閱動態標籤管理產品文件的[快速入門](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html)。

如需詳細資訊，請參閱[使用 Dynamic Tag Management 實作 Analytics](/help/implement/c-implement-with-dtm/dtm-implementation-overview.md)。

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

JavaScript 實施方法需要您手動在頁面上設定 JavaScript 程式碼。如果您使用 Expereience Platform Launch 或 Dynamic Tag Management 實施方法，可將此工作的絕大部分加以簡化。不過，部分使用者可能需要 JavaScript 方法。

JavaScript 實施需要:

* 高強的 JavaScript 技能
* 對 Analytics 概念與術語有深厚瞭解

如需詳細資訊，請參閱[使用 JavaScript 實作 Analytics](/help/implement/js-implementation/javascript-implementation-overview.md)。
