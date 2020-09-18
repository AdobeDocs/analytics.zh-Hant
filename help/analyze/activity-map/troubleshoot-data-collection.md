---
title: 疑難排解Activity Map資料收集
description: 確定影像請求中看不到Activity Map資料的原因
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%

---


# 疑難排解Activity Map資料收集

如果您未看到Activity Map維度的資料，請使用此頁面協助判斷原因。

## 使用除錯程式確認資料收集

首先，請確定AppMeasurement會正確收集Activity Map資料。

1. Download and install the [Adobe Experience Cloud Debugger Chrome Extension](https://docs.adobe.com/content/help/zh-Hant/debugger/using/experience-cloud-debugger.html).
2. 導覽至您的網頁，然後按一下連結。
3. 當後續頁面載入時，請開啟除錯程式。 驗證您是否看到Activity Map上下文資料變數夾在 `activitymap.` 和 `.activitymap`:

![除錯程式資料](assets/debugger.png)

## Activity Map資料不存在的可能原因

檢查下列各項，以確認Activity Map元件是否存在：

* **AppMeasurement版本**:v1.6和更高版本支援Activity Map。 當您升級至最新穩定版AppMeasurement時，會解決許多邊緣案例問題。
* **Activity Map模組**:檢查檔案 `AppMeasurement_Module_Activity_Map` 中是否存在模 `AppMeasurement.js` 塊。 如果您的實作使用Adobe Experience Platform Launch，請確定在「連結追蹤」下設定Analytics擴充功能時已勾選「 **[!UICONTROL Enable ClickMap]** 」（啟用ClickMap） **[!UICONTROL 功能]**。
* **Cookie`s_sq`**:Activity Map取決於資 `s_sq` 料收集的Cookie。
   * 請確定變數 `cookieDomainPeriods` 已正確設定，尤其是區域網域(如 `*.co.uk` 或 `*.co.jp`)。
   * 請確定變 `linkInternalFilters` 數已設定為所需值。 如果點按的連結不符合內部篩選，Activity Map會將其視為退出連結，而不會收集資料。
* **Activity Map覆蓋正在執行**:啟用Activity Map覆蓋後，AppMeasurement不會追蹤您網頁的點按資料。
