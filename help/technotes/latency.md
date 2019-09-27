---
description: The following information can help troubleshoot report suite latency issues in Analytics data.
keywords: 丟失資料；慢速
seo-description: 下列資訊可協助疑難排解Analytics資料中的報表套裝延遲問題。
seo-title: Data availability and latency
solution: Analytics
subtopic: 目前的資料
title: Data availability and latency
topic: 報表
uuid: 1f0e67e3-6cea-4af8-8b18-7ae9223df7c8
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Data availability and latency in Adobe Analytics

通常，在收集資料後2小時內，您會預期報表中會顯示完整的資料。 下列資訊可協助疑難排解Analytics資料中的報表套裝延遲問題。

## 瞭解資料批次處理

每一個資料收集伺服器擷取和處理原始分析資料，然後每小時上傳批次的資料以便報告。傳輸程序通常要花 30 分鐘，因此在前一個上傳程序完成之後緊接著出現的正常流量延遲大約是 90 分鐘 (到下一次批次上傳還有 60 分鐘，然後檔案轉輸及顯示又要 30 分鐘)。For traffic that occurs directly before an upload, data latency could be as short as 30 minutes (0 minutes until the next batch upload occurs, then 30 minutes for file transfer and display).

If needed, Adobe Customer Care can enable 30 minute batched data uploads (instead of hourly) for your most-used report suites.

## Contributors to latency

Latency is a delay that is longer than the typical 2 hours it takes for data collection servers to fully process data. 它不影響資料收集；無論報表套裝的潛在性為何，仍會收集工作實作的資料。 Its severity (how current the data is) and length (the time it takes to resolve) can vary greatly. It is usually limited to a single report suite.

延遲導因於下列一般類別之一:

* **** 非預期的流量尖峰：當傳送的資料比合約約定或預期的要多時，即會發生此類延遲。 這是發生延遲最常見的原因。
* **** 一般硬體問題：Adobe運用同級最佳的策略來管理和監控資料中心、資料備援以及硬體可靠性。 硬體除了會定期更新，也會配合發佈的維護時程進行更新。當更換硬體上線時，緊急維護故障硬體可能需要在資料處理中暫停（而非在資料收集中）。 這樣的暫停處理可能導致相當程度的延遲。
* **** Abnormal data: Unnatural data patterns, such as unusually long visits caused by a bot or crawler, can temporarily increase certain processing loads that result in latency.

## 依賴延遲的功能

Adobe Experience cloud中的某些功能，除了標準處理時間之外，還有先天的延遲量。

* Analytics for Target(A4T)需要額外5-10分鐘的延遲，才能將來自兩個平台的收集資料儲存在相同的點擊中。
* 時間戳記資料需要額外的時間，因為會處理資料的伺服器不同。 即時或接近即時收到的時間戳記點擊最多需要15分鐘。 以昨天時間戳記收到的點擊最多需要2小時。 較舊的點擊可能需要更長的時間，每天增加最多約24小時。

## 降低或防止延遲的方法

有幾種策略可防止延遲，或縮短延遲的復原時間:

* **** 預期的流量尖峰通知Adobe:雖然您無法預測網站的每個流量尖峰，但有時您可能會預期流量會大幅增加。 例如，特別成功的假期，或大型促銷活動推播後不久。 針對這些情況，Adobe 備有適當管道可供您的組織回報預期的流量增加，好讓我們為您的報表套裝額外配置處理資源。請參 [閱「管理員使用指南](../admin/c-traffic-management/t-traffic-schedule-spike.md) 」中的「排程流量尖峰」，瞭解如何通知Adobe流量增加。
* **** 啟動新功能時，請考慮處理負載：有些功能的處理密集程度高於其他功能。 在報表套裝上啟用的功能愈多，延遲的復原難度就愈高。在報表套裝上啟用功能時，請留意下列會增加處理資料量的功能:

   * 在相同頁面上實作超過20個事件
   * 複雜的 VISTA 規則
   * 產品變數中有超過 20 個值
   * 事件序列化

* Enable IAB Bot filtering: [Bot filtering](https://marketing.adobe.com/resources/help/en_US/admin/c_bot_rules.html) can greatly reduce latency if your report suite is frequented by bots or crawlers. 建議您使用 IAB 機器人清單，因為這份清單是由 [Interactive Advertising Bureau](https://www.iab.net/about_the_iab) 負責更新及維護的。使用者可自訂自己的機器人規則，以彌補IAB的不足。

## 如何處理延遲問題

在發生延遲時，請放心Adobe會主動監控處理管道，並盡可能盡快將處理時間回復正常。 延遲問題大多可在幾小時內解決。如果您擔心特定報告套裝可能有延遲，可由組織的「受支援使用者」之一聯絡客戶服務，並回報發生延遲的報告套裝 ID。Adobe 代表會驗證延遲問題，並在問題改善並解決時通知您。
