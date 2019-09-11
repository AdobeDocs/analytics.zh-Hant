---
title: 跨裝置分析
description: 跨裝置Analytics可將裝置資料整合在一起，將您的資料從裝置導向轉為個人焦點。
translation-type: tm+mt
source-git-commit: 40d8ecae1ac7e0a1df4a2df17f5104bee6ecf336

---


# 跨裝置分析

> [!NOTE] 跨裝置Analytics文件可能會隨著進一步開發功能而變更。定期回來查看更新。

跨裝置分析功能可將Analytics從裝置導向檢視轉變為人員導向檢視。此功能使用Adobe Experience Platform Identity Service Co-op圖表或私人圖形來識別屬於個人的裝置，並將它們接合在一起。因此，分析師可以瞭解超越瀏覽器、裝置或應用程式的使用者行為。使用 CDA，您可以回答下列問題:

* 有多少人正在與我的品牌互動? 他們使用的裝置數量與類型為何? 他們互相重疊的程度?
* 人們會在行動裝置上開始工作，稍後再移至桌上型電腦完成工作的頻率為何? 登陸在一部裝置上的行銷活動點進次數，是否會導致在其他位置上的轉換?
* 如果將跨裝置歷程列入考量，我對行銷活動成效的理解會有何改變? 我的漏斗分析會有何改變?
* 使用者在裝置間移動最常採取的路徑為何? 他們在哪裡退出? 他們在哪裡獲得成功?
* 多部裝置使用者的行為與單一裝置使用者的行為有何不同?

當裝置接合時，會跨裝置保留變數持續性。例如，使用者首先透過桌上型電腦上的廣告瀏覽您的網站。該使用者會找到您的行動應用程式，並安裝它，然後在他們的行動裝置上購買。透過跨裝置分析，收入可以歸因於他們在桌上型電腦上點選的廣告。

請參閱 [歷程IQ：跨裝置Analytics Spark頁面](http://adobe.ly/aacda) ，進一步瞭解跨裝置分析的功能和功能。

## 必備條件

自2019年月起，跨裝置分析需要下列各項。與組織內的團隊和Adobe客戶經理合作，確保您符合下列所有事項。

> [!IMPORTANT] 如果無法滿足所有必要條件，可能導致跨裝置Analytics無法啓用跨裝置分析或聯繫資料。

* 貴組織的資料必須位於Adobe太平洋西北地區資料中心。預計在其他地區的資料中心支援資料中心。
* 請聯絡組織的客戶經理以建立這些要點：
   * 合約必須與Adobe簽署，其中包含Adobe Analytics Ultimate。
   * 您的組織必須使用Adobe Experience Platform Identity Service Co-op Graph或Private Graph。請參閱Device Co-op使用指南中的 [首頁](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) 。
   * 貴組織必須同意允許Adobe在Microsoft Azure伺服器上處理和儲存Analytics資料。Adobe使用Azure儲存裝置圖形資料並執行裝置接合。因此，Adobe Analytics資料會在Adobe的資料處理中心與Adobe在Microsoft Azure中的呈現之間來回傳遞。
* 跨裝置分析是根據每個報表套裝啓用。您的報表套裝需要下列項目：
   * 目前，報告套裝每天不能有超過億次點擊。這個臨界值會在未來幾個月增加。
   * 「跨裝置」報表套裝，表示所有裝置上的所有資料都必須傳送至相同的報表套裝。有些組織將此稱為「全域」報表套裝，但CDA並不嚴格必須是地理位置的全域。跨裝置Analytics無法跨報告套裝運作。
* 您的實作必須符合下列需求：
   * 必須部署最新版本的Experience Cloud ID服務。請參閱Experience [Cloud](https://docs.adobe.com/content/help/en/id-service/using/home.html) Identity Service使用指南中的首頁。大部分使用Adobe Experience Platform Launch的實作都可能已部署ECID。
   * 每當可以識別個人時呼叫 `setCustomerIDs` 函數，例如當使用者登入或開啓電子郵件時。此項需求適用於所有平台，包括行動應用程式。請參閱 [Experience](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) Cloud Identity Service使用指南中的setCustomerIDs。

## 限制

跨裝置分析是一項突破性且強大的功能，但對於它的使用有一些限制。

* CDA僅適用於分析工作區。
* 聯結無法跨IMS組織進行。請確定您未在實施中使用多個IMS Orgs。
* 無法如上面的「必要條件」所述，跨報告套裝進行裝訂。
* CDA目前不相容於客戶屬性。客戶屬性無法用來建立CDA虛擬報表套裝、跨裝置區段內的報告，或用於以CDA虛擬報表套裝為基礎的分析工作區專案中的報告。
* CDA需要Co-op圖表或私人圖形。不支援第三方裝置圖表。
* 不支援舊版Analytics ID。僅會銜接具有Experience Cloud ID的訪客。
* 客戶服務尚未完全支援此功能。[跨裝置分析論壇](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) 可用來支援這項功能，其中包括Adobe產品經理主動與直接參與。
* 跨裝置Analytics使用虛擬報表套裝和報告時間處理，其本身有其限制。如需這些限制的詳細資訊，請參閱 [虛擬報表套裝](../vrs/vrs-about.md) 和 [報告時間處理](../vrs/vrs-report-time-processing.md) 。
* 瀏覽您網站的新裝置可能需要兩周的時間，才能由Co-op圖形或私密圖形處理。CDA在最近兩周的接合程度通常低於兩周之前的日期範圍。Adobe計劃改進Adobe Experience Platform Identity Service，在未來即時扼殺新裝置。
* 虛擬報表套裝中的歷史資料會根據Adobe識別和銜接裝置而變更。來源報表套裝中的資料不會變更。

一旦您的組織符合所有需求並瞭解限制，您可以開始 [設定跨裝置分析](cda-setup.md)。
