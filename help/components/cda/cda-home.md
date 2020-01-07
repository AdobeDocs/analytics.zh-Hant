---
title: 跨裝置分析
description: 跨裝置分析將裝置資料連結在一起，將資料從以裝置為中心轉變為以人為中心。
translation-type: ht
source-git-commit: c358df811f23a57441e6f9410c957e34954de712

---


# 跨裝置分析

> [!NOTE] 跨裝置分析文件內容可能會隨著功能的進一步開發而有所變更。請定期回訪以取得更新內容。

跨裝置分析功能將 Analytics 從裝置導向檢視轉變為以人為導向的檢視。此功能使用 Adobe Experience Platform Identity Service 合用圖表或專用圖表來識別屬於個人的裝置，並將它們連結在一起。因此分析師可以瞭解跨瀏覽器、裝置或應用程式的使用者行為。使用 CDA，您可以回答下列問題:

* 有多少人正在與我的品牌互動? 他們使用的裝置數量與類型為何? 他們互相重疊的程度?
* 人們會在行動裝置上開始工作，稍後再移至桌上型電腦完成工作的頻率為何? 登陸在一部裝置上的行銷活動點進次數，是否會導致在其他位置上的轉換?
* 如果將跨裝置歷程列入考量，我對行銷活動成效的理解會有何改變? 我的漏斗分析會有何改變?
* 使用者在裝置間移動最常採取的路徑為何? 他們在哪裡退出? 他們在哪裡獲得成功?
* 多部裝置使用者的行為與單一裝置使用者的行為有何不同?

當裝置連結時，變數的持續存在性會跨裝置傳遞。例如，某位使用者先透過桌上型電腦上的廣告造訪您的網站。該使用者找到您的行動應用程式並安裝，最終在其行動裝置上進行購買。透過跨裝置分析功能，可將收入歸因於使用者在桌上型電腦上點按的廣告。

請參閱[歷程 IQ: 跨裝置分析 Spark 頁面](http://adobe.ly/aacda)，進一步瞭解跨裝置分析的功能和特色。

## 必要條件

自 2019 年 9 月起，使用跨裝置分析功能須達到下列要求。請與組織內部團隊及 Adobe 客戶經理合作，確保您符合以下所有條件。

> [!IMPORTANT] 若未符合所有必要條件，可能會導致無法啟用跨裝置分析功能，或在連結資料時效果不彰。

* 貴組織的資料必須存放於 Adobe 的太平洋西北地區資料中心。已規劃為全球其他地區的資料中心提供支援。
* 請聯絡貴組織的客戶經理以確立下列關鍵點:
   * 必須與 Adobe 簽署包含 Adobe Analytics Ultimate 的合約。
   * 貴組織必須使用 Adobe Experience Platform Identity Service 合用圖表或專用圖表。請參閱 Device Co-op 使用指南中的[首頁](https://docs.adobe.com/content/help/zh-Hant/device-co-op/using/home.html)。
   * 貴組織必須同意允許 Adobe 在 Microsoft Azure 伺服器上處理及儲存 Analytics 資料。Adobe 使用 Azure 來儲存裝置圖表資料及執行裝置連結。因此，Adobe Analytics 資料會在 Adobe 的資料處理中心與 Adobe 所採用的 Microsoft Azure 之間來回傳遞。
* 系統會根據報表套裝啟用跨裝置分析功能。已啟用 CDA 的報表套裝須達到以下條件:
   * 報表套裝每天的點擊數不能超過 1 億次。此門檻將在未來幾個月內提高。
   * Adobe 建議報表套裝中包含跨裝置資料，也就是來自多種裝置類型 (網頁、應用程式等) 的資料。某些組織將此概念稱為「全域」報表套裝，但從地理角度來說 CDA 不見得須為全域。跨裝置分析功能無法跨報表套裝運作，也無法合併來自多個報表套裝的資料。
* 您的實作必須符合下列最低要求:
   * 必須部署最新版的 Experience Cloud ID Service。請參閱 Experience Cloud Identity Sservice 使用指南中的[首頁](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.html)。大部分使用 Adobe Experience Platform Launch 的實作可能都已部署 ECID。
   * 每當可識別個人身分時 (例如使用者登入或開啟電子郵件)，就會呼叫 `setCustomerIDs` 函式。這項要求適用於所有平台，包括行動應用程式在內 (若有使用)。請參閱 Experience Cloud Identity Service 使用指南中的 [setCustomerIDs](https://docs.adobe.com/content/help/zh-Hant/id-service/using/id-service-api/methods/setcustomerids.html)。

## 限制

跨裝置分析是一項具突破性且完善的功能，但其使用方式有所限制。

* CDA 只能透過 Analysis Workspace 使用。
* 如上述必要條件所說明，無法跨報表套裝進行連結。
* Adobe Analytics 報表套裝無法對應至多個 IMS 組織。由於 CDA 會連結一個指定報表套裝中的裝置，因此 CDA 無法用於連結跨多個 IMS 組織的資料。
* CDA 目前與客戶屬性不相容。客戶屬性不能用來在跨裝置區段內建立 CDA 虛擬報表套裝，也不能用來在以 CDA 虛擬報表套裝為基礎的 Analysis Workspace 專案內的建立報表。
   > [!TIP] 雖然客戶屬性無法在 CDA 中使用，但這兩項功能都需依賴 `setCustomerIDs` 功能。這兩個功能可在個別 (虛擬) 報表套裝中保持一致。
* CDA 需使用合用圖表或專用圖表。不支援第三方裝置圖形。
* 不支援舊式 Analytics ID。只會連結具有 Experience Cloud ID 的訪客。
* 客戶服務尚未完全支援此功能。可使用[跨裝置分析論壇](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview)來支援這項功能，包括 Adobe 產品經理的主動與直接參與。
* 跨裝置分析使用虛擬報表套裝和報表時間處理，且各有其專屬的限制。如需這些限制的詳細資訊，請參閱[虛擬報表套裝](../vrs/vrs-about.md)和[報表時間處理](../vrs/vrs-report-time-processing.md)。
* 1.4 API 不受支援。Power BI 連接器和 Report Builder 都需依賴 1.4 API，因此與 CDA 不相容。
* 當有新裝置造訪您的網站，由「合用圖表」或「專用圖表」進行處理最多需要兩週時間。CDA 中最近兩週的連結程度通常低於兩週以前的日期範圍。Adobe 計畫改善 Adobe Experience Platform Identity Service 未來即時連結新裝置的效能。
* 虛擬報表套裝中的歷史資料會隨著 Adobe 識別和連結裝置而改變。來源報表套裝中的資料不會變更。

貴組織達到所有要求並瞭解相關限制後，您就可以開始[設定跨裝置分析](cda-setup.md)。
