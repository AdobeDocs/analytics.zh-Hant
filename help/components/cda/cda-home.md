---
title: Cross-Device Analytics
description: 跨裝置分析將裝置資料結合在一起，將您的資料從以裝置為中心變更為以人為中心。
translation-type: tm+mt
source-git-commit: c358df811f23a57441e6f9410c957e34954de712

---


# Cross-Device Analytics

> [!NOTE] 跨裝置分析檔案可能會隨著功能的進一步開發而變更。 請定期回訪以取得更新。

跨裝置分析是一種功能，可將Analytics從裝置導向檢視轉換為人本導向檢視。 此功能使用Adobe Experience Platform Identity Service Co-op Graph或Private Graph來識別屬於個人的裝置，並將它們結合在一起。 因此，分析師可以瞭解跨瀏覽器、裝置或應用程式的使用者行為。 使用 CDA，您可以回答下列問題:

* 有多少人正在與我的品牌互動? 他們使用的裝置數量與類型為何? 他們互相重疊的程度?
* 人們會在行動裝置上開始工作，稍後再移至桌上型電腦完成工作的頻率為何? 登陸在一部裝置上的行銷活動點進次數，是否會導致在其他位置上的轉換?
* 如果將跨裝置歷程列入考量，我對行銷活動成效的理解會有何改變? 我的漏斗分析會有何改變?
* 使用者在裝置間移動最常採取的路徑為何? 他們在哪裡退出? 他們在哪裡獲得成功?
* 多部裝置使用者的行為與單一裝置使用者的行為有何不同?

當裝置接合時，可變永續性會跨裝置傳遞。 例如，使用者先透過桌上型電腦上的廣告瀏覽您的網站。 該使用者會找到您的行動應用程式，並加以安裝，最終在其行動裝置上進行購買。 透過跨裝置分析，收入可歸因於他們在桌上型電腦上點按的廣告。

請參閱 [歷程IQ:跨裝置分析Spark頁面](http://adobe.ly/aacda) ，以進一步瞭解跨裝置分析的功能和功能。

## 必備條件

自2019年9月起，跨裝置分析需要下列項目。 與組織內的團隊及Adobe客戶經理合作，確保您符合下列所有條件。

> [!IMPORTANT] 無法符合所有必要條件可能會導致無法啟用跨裝置分析，或在拼接資料時造成結果不佳。

* 貴組織的資料必須位於Adobe的太平洋西北地區資料中心。 計畫為世界其他地區的資料中心提供支援。
* 請連絡您組織的客戶經理以建立以下關鍵點：
   * 必須與Adobe簽署包含Adobe Analytics Ultimate的合約。
   * 您的組織必須使用Adobe Experience Platform Identity Service Co-op Graph或Private Graph。 請參 [閱Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) 使用指南中的首頁。
   * 貴組織必須同意允許Adobe在Microsoft Azure伺服器上處理及儲存Analytics資料。 Adobe使用Azure來儲存裝置圖表資料並執行裝置拼接。 因此，Adobe Analytics資料會在Adobe的資料處理中心與Adobe在Microsoft Azure的存在之間來回傳遞。
* 跨裝置分析會依每個報表套裝啟用。 已啟用CDA的報表套裝需要：
   * 報表套裝每天的點擊數不能超過1億次。 這一門檻將在未來幾個月內提高。
   * Adobe建議報表套裝包含跨裝置資料，這表示來自多種裝置類型（網路、應用程式等）的資料。 有些組織將此概念稱為「全域」報表套裝，但CDA並非從地理角度來說完全為全域。 跨裝置分析無法跨報表套裝運作，也無法合併來自多個報表套裝的資料。
* 您的實作必須符合下列要求：
   * 必須部署最新版的Experience Cloud ID服務。 請參 [閱Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/home.html) Identity service使用指南中的首頁。 大部分使用Adobe Experience Platform Launch的實作可能已部署ECID。
   * 只要可 `setCustomerIDs` 以識別個人（例如使用者登入或開啟電子郵件），就呼叫函式。 這項要求適用於所有平台，包括使用時的行動應用程式。 請參 [閱Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) Identity service使用指南中的setCustomerIDs。

## 限制

跨裝置分析是一項突破性且強穩的功能，但其使用方式有限。

* CDA僅能透過分析工作區使用。
* 無法如上述先決條件所述跨報表套裝進行拼接。
* Adobe Analytics報表套裝無法對應至多個IMS組織。 由於CDA可在指定的報表套裝中連接裝置，因此CDA無法用於將資料接合在多個IMS組織中。
* CDA目前與「客戶屬性」不相容。 「客戶屬性」不能用來建立CDA虛擬報表套裝、跨裝置區段，或用來建立以CDA虛擬報表套裝為基礎的「分析」工作區專案內的報表。
   > [!TIP] 雖然CDA中無法使用客戶屬性，但這兩項功能都依賴於功 `setCustomerIDs` 能。 這兩個功能可在個別（虛擬）報表套裝中保持一致。
* CDA需要「合作圖」或「私用圖」。 不支援協力廠商裝置圖形。
* 不支援舊版Analytics ID。 只有具有Experience Cloud ID的訪客會被縫紉。
* 客戶服務尚未完全支援此功能。 跨 [裝置分析論壇](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) ，可用來支援這項功能，包括Adobe產品經理主動且直接參與。
* 跨裝置分析使用虛擬報表套裝和報表時間處理，有其自己的限制。 如需 [這些限制的詳細資訊](../vrs/vrs-about.md) ，請參 [](../vrs/vrs-report-time-processing.md) 閱虛擬報表套裝和報表時間處理。
* 不支援1.4 API。 Power BI連接器和Report builder都仰賴1.4 API，因此與CDA不相容。
* 造訪您網站的新裝置最多需要兩週時間，才能由「合作圖」或「私人圖」處理。 CDA中最近兩週的拼接程度通常低於兩週以前的日期範圍。 Adobe計畫改善Adobe Experience Platform Identity Service，在未來即時連接新裝置。
* 虛擬報表套裝中的歷史資料會根據Adobe識別和連結裝置而改變。 來源報表套裝中的資料不會變更。

在貴組織符合所有需求並瞭解其限制後，您就可以開始 [設定跨裝置分析](cda-setup.md)。
