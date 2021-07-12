---
title: 疑難排解Activity Map資料收集
description: 判斷影像要求中為何看不到Activity Map資料
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%

---

# 疑難排解Activity Map資料收集

如果您沒有看見Activity Map維度的資料，請使用本頁面來協助判斷原因。

## 使用除錯工具確認資料收集

首先，請確定AppMeasurement正確收集Activity Map資料。

1. 下載並安裝[Adobe Experience Cloud Debugger Chrome擴充功能](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hant)。
2. 導覽至您的網頁，然後按一下連結。
3. 後續頁面載入時，請開啟除錯工具。 驗證您是否看見夾在`activitymap.`和`.activitymap`之間的Activity Map內容資料變數：

![除錯工具資料](assets/debugger.png)

## Activity Map資料不存在的可能原因

檢查下列各項，確認有Activity Map元件：

* **AppMeasurement版本**:Activity Map支援v1.6及更高版本。升級至最新穩定版的AppMeasurement時，可解決許多邊緣案例問題。
* **Activity Map模組**:檢查檔 `AppMeasurement_Module_Activity_Map` 案中是否有模 `AppMeasurement.js` 組。如果您的實作使用Adobe Experience Platform Launch，在&#x200B;**[!UICONTROL 連結追蹤]**&#x200B;下設定Analytics擴充功能時，請確定已勾選&#x200B;**[!UICONTROL 啟用ClickMap]**。
* **`s_sq` Cookie**:Activity Map取決於 `s_sq` 資料收集的Cookie。
   * 請確定`cookieDomainPeriods`變數已正確設定，尤其是針對`*.co.uk`或`*.co.jp`等區域網域。
   * 請確定`linkInternalFilters`變數已設為所需值。 如果點按的連結與內部篩選器不符，Activity Map會將其視為退出連結，而不會收集資料。
* **Activity Map覆蓋執行中**:啟用Activity Map覆蓋圖時，AppMeasurement不會追蹤您網頁的點按資料。
