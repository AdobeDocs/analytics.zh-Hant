---
title: 交易 ID 資料來源
description: 使用線上點選的儲存值，讓共用交易ID的離線點選更為豐富。
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: 0a65114d598b7c6d2871a2446ad4d574b9ca44bb
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 8%

---

# 交易 ID 資料來源

交易ID資料來源是摘要資料來源的變化，可讓您將從線上點選儲存的值套用至共用相同交易ID的離線列。 當您線上上擷取交易，但稍後從其他系統接收詳細資訊時，此方法很有用。 主要範例包括產品退貨、預訂取消或客服中心互動的結果。

>[!NOTE]
>
>在使用交易ID資料來源之前，您必須先在所需報表套裝的[一般帳戶設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)中啟用它。

## 運作方式

交易ID的概念需要兩個部分：

* **線上點選**：任何傳送至報表套裝(AppMeasurement、Web SDK、API等)的完整Analytics點選。 您在此點選上設定[`transactionID`](/help/implement/vars/page-vars/transactionid.md)實作變數。
* **離線點選**：透過資料來源上傳的列。 在檔案中，加入`transactionID`欄，其值與線上點選相符。

當您傳送包含`transactionID`實作變數的線上點選時，Adobe會對當時所設定或持續存在的下列維度拍攝「快照」：

* [類別](/help/components/dimensions/category.md)
* [首次購買間隔天數](/help/components/dimensions/days-before-first-purchase.md)
* [上次購買間隔天數](/help/components/dimensions/days-since-last-purchase.md)
* [eVars 1-250](/help/components/dimensions/evar.md)
* 在[報告套裝設定](/help/admin/admin/c-manage-report-suites/report-suites-admin.md)中啟用的功能特定維度，其行為與eVar類似。 行為類似於prop的特徵特定維度不包括在內。
* [清單變數](/help/implement/vars/page-vars/list.md)
* [行銷管道](/help/components/dimensions/marketing-channel.md)
* [行銷管道詳細資料](/help/components/dimensions/marketing-detail.md)
* [行動維度](/help/components/dimensions/mobile-dimensions.md)
* [原始反向連結網域](/help/components/dimensions/original-referring-domain.md)
* [產品](/help/components/dimensions/product.md)
* [反向連結網域](/help/components/dimensions/referring-domain.md)
* [搜尋引擎](/help/components/dimensions/search-engine.md)
* [搜尋關鍵字](/help/components/dimensions/search-keyword.md)
* [追蹤代碼](/help/components/dimensions/tracking-code.md)
* [造訪次數](/help/components/dimensions/visit-number.md)

>[!NOTE]
>
>量度（例如[訂單](/help/components/metrics/orders.md)或[自訂事件](/help/components/metrics/custom-events.md)）未包含在「快照」中。

當您透過包含相符交易ID的資料來源上傳離線點選時，「快照」內的任何可用維度都會自動附加至資料來源列。 如果指定的維度同時存在於線上和離線點選中，則會使用離線點選值。

>[!IMPORTANT]
>
>交易ID資料來源的概念，只會有助於填入資料來源列（離線點選）。 它們不會影響或變更線上點選。

## 交易ID資料來源考量事項

交易ID資料來源有下列屬性：

* 必須先收集和處理線上資料。 如果交易ID資料來源是在報表套裝處理符合該交易ID的點選之前上傳，則會將資料視為摘要資料來源。
* 從線上點選收集到的交易ID會在25個月後過期。
* 以過期交易ID上傳的資料來源，其處理方式與沒有交易ID上傳的資料類似。
* 如果您在多個線上點選上設定相同的交易ID，則只會使用第一個事件的「快照」。 後續的重複交易ID線上點選會依沒有交易ID的方式進行處理。
* 一旦您填入指定的`transactionID`值，關聯的「快照」將視為在該交易ID過期之前不可變動。
* 如果您在多個資料來源列上設定相同的交易ID，則線上點選中的任何可用維度都會附加至每個離線點選。 相同交易ID的離線點選彼此之間不瞭解任何內容；資料不會在離線點選之間傳遞。
