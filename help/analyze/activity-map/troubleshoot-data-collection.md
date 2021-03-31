---
title: 疑難排解Activity Map資料收集
description: 確定在影像請求中看不到Activity Map資料的原因
feature: Activity Map
role: 業務從業人員、管理員
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 3%

---


# 疑難排解Activity Map資料收集

如果您未看到Activity Map維度的資料，請使用此頁面協助判斷原因。

## 使用除錯程式確認資料收集

首先，請確定AppMeasurement正確收集Activity Map資料。

1. 下載並安裝[Adobe Experience Cloud偵錯器Chrome Extension](https://docs.adobe.com/content/help/zh-Hant/debugger/using/experience-cloud-debugger.html)。
2. 導覽至您的網頁，然後按一下連結。
3. 當後續頁面載入時，請開啟除錯程式。 驗證您是否看到Activity Map上下文資料變數夾在`activitymap.`和`.activitymap`之間：

![除錯程式資料](assets/debugger.png)

## Activity Map資料不存在的可能原因

檢查以下各項，確保Activity Map元件存在：

* **AppMeasurement版本**:Activity Map在v1.6和更高版本上受支援。當您升級至最新穩定版AppMeasurement時，會解決許多邊緣案例問題。
* **Activity Map模組**:檢查檔案 `AppMeasurement_Module_Activity_Map` 中是否存在模 `AppMeasurement.js` 塊。如果您的實作使用Adobe Experience Platform Launch，請確定在&#x200B;**[!UICONTROL 連結追蹤]**&#x200B;下設定Analytics擴充功能時已勾選&#x200B;**[!UICONTROL 啟用ClickMap]**。
* **Cookie `s_sq`**:Activity Map取決於 `s_sq` 資料收集的Cookie。
   * 請確定`cookieDomainPeriods`變數已正確設定，尤其是針對地區網域，例如`*.co.uk`或`*.co.jp`。
   * 請確定`linkInternalFilters`變數已設為所需值。 如果點按的連結不符合內部篩選，Activity Map會將其視為退出連結，而不會收集資料。
* **Activity Map覆蓋執行**:啟用Activity Map覆蓋後，AppMeasurement不會追蹤您網頁的點按資料。
