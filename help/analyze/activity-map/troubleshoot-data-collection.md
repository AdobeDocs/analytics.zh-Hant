---
title: 疑難排解Activity Map資料收集
description: 判斷影像要求中為何看不到Activity Map資料
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# 疑難排解Activity Map資料收集

如果您沒有看見Activity Map維度的資料，請使用本頁面來協助判斷原因。

## 使用除錯工具確認資料收集

首先，請確定AppMeasurement正確收集Activity Map資料。

1. 下載並安裝 [Adobe Experience Cloud Debugger Chrome擴充功能](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hant).
2. 導覽至您的網頁，然後按一下連結。
3. 後續頁面載入時，請開啟除錯工具。 驗證您是否看到Activity Map上下文資料變數夾在 `activitymap.` 和 `.activitymap`:

![除錯工具資料](assets/debugger.png)

## Activity Map資料不存在的可能原因

檢查下列各項，確認有Activity Map元件：

* **AppMeasurement版本**:Activity Map支援v1.6及更高版本。 升級至最新穩定版的AppMeasurement時，可解決許多邊緣案例問題。
* **Activity Map模組**:檢查 `AppMeasurement_Module_Activity_Map` 模組存在於 `AppMeasurement.js` 檔案。 如果您的實作使用Adobe Experience Platform來收集資料，請確定 **[!UICONTROL 啟用ClickMap]** 在下設定Analytics擴充功能時，會勾選 **[!UICONTROL 連結追蹤]**.
* **此 `s_sq` cookie**:Activity Map取決於 `s_sq` 用於資料收集的cookie。
   * 請確定 `cookieDomainPeriods` 變數已正確設定，尤其是針對區域網域，例如 `*.co.uk` 或 `*.co.jp`.
   * 請確定 `linkInternalFilters` 變數設為所需的值。 如果點按的連結與內部篩選器不符，Activity Map會將其視為退出連結，而不會收集資料。
* **Activity Map覆蓋執行**:啟用Activity Map覆蓋圖時，AppMeasurement不會追蹤您網頁的點按資料。
