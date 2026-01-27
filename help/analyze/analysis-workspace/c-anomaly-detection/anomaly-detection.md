---
description: 了解 Analysis Workspace 中的資料異常偵測。
title: 異常偵測概觀
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '1292'
ht-degree: 100%

---

# 異常偵測概觀

您可以在 Analysis Workspace 中根據情境來檢視和分析資料異常。貢獻度分析與異常偵測搭配運作，可識別導致異常的因素。


>[!BEGINSHADEBOX]

請參閱![影片簽出](/help/assets/icons/VideoCheckedOut.svg)[異常偵測](https://video.tv.adobe.com/v/25444?quality=12&learn=on){target="_blank"}，以觀看示範影片。

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Adobe Analytics Select 和 Adobe Analytics Foundation 客戶僅可在 Workspace 中存取&#x200B;*每日顆粒度*&#x200B;的異常偵測。如需更多資訊，請參閱[異常偵測和貢獻度分析權限](#anomaly-detection-and-contribution-analysis-entitlements)。

## 異常偵測

「異常偵測」提供一種統計方法，以判斷指定的量度和先前的資料比較有何變更。

異常偵測讓您能夠將「真實信號」與「噪音」區分開來，並進一步找出可能對這些信號或異常產生影響的因素。換句話說，此偵測功能協助您確認哪些統計波動具有重要性，哪些則不重要。接著，您可以找出真正異常的根本原因。此外，您還可以獲得可靠的量度 (KPI) 預測。

您可能會調查的異常例子包括：

* 平均訂購值的劇烈下降
* 訂單激增但低收入
* 試用版註冊數量激增或下降
* 登陸頁面檢視次數下降
* 影片緩衝事件激增
* 低影片位元速率激增

異常偵測和[貢獻度分析](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)是 Analysis Workspace 中的核心工作流程。您可以對任何每日異常執行貢獻度分析，並將結果嵌入到您的 Analysis Workspace 專案中。

Analysis Workspace 的異常偵測演算法包括

* 除了現有的每日顆粒度，另支援對每小時、每週和每月的顆粒度。
* 意識到季節性 (如「黑色星期五」) 和假期的情形。

## 貢獻分析

貢獻度分析能夠發現資料中隱藏的模式，以解釋統計異常並識別其背後的關聯

* 意外的客戶行為，
* 超出範圍的數值，以及
* 突然的激增或下降

涵蓋聚合式客群細分群體的選定量度。


>[!BEGINSHADEBOX]

請參閱![影片簽出](/help/assets/icons/VideoCheckedOut.svg)[貢獻度分析](https://video.tv.adobe.com/v/25443?quality=12&learn=on){target="_blank"}，以觀看示範影片。

>[!ENDSHADEBOX]


發生異常。原因為何？異常偵測報表顯示訂購中有不尋常的尖峰，您想知道為什麼。發生什麼反常的事？誰正在回應哪個促銷活動或轉接？中毒了嗎？什麼特定因素造成這個異常現象？而最重要的可能是：我如何獲取有關客戶的重要資訊，並重複這表現？(或者，如果發生量度下降或是負量度上升，我日後要如何避免？)

貢獻分析能幫助您立即評估資料，解答異常為何發生。其只需幾秒鐘而不是像過去要花費數週來把異常的貢獻度分解完成，並提供客群細分群體的模式，幫助您針對客戶互動發展出一套敘事。您可以策略性地使用貢獻度分析來確認和獲取有意義的關聯。然後，策略性地使用這些關聯來開發新的客群細分群體，或戰術性地找出觸發警報的超出範圍或欺詐的活動。

[異常偵測](#anomaly-detection)可根據選取的量度和選取的客群細分群體來確認資料尖峰和統計數據極端下降的情況。異常偵測根據訓練期間設下歷史常規，然後繪製與特定事件相關的極端偏移情形。異常偵測可以報告正向訂單量度的急劇上升，或負向的跳出量度的上升，或者兩者的下降，並獲取統計相關的資料點，以便由貢獻度分析進行評估。一旦識別出統計異常，貢獻度分析讓您深入研究並評估所有異常資料點中相關的行銷和活動變數。其執行先進的演算法和機器學習程序，以評估造成激烈增加或下降的關聯性。這些計算接著會透過互動式視覺效果的方式顯示，為您提供各種不同觀點，以便了解發生特定現象的原因，以及因應的方式。

貢獻度分析幫助您發展敘事，描述異常發生的原因。以及如何回應異常，獲取相關的量度並發現隱藏的要點，讓您了解客群互動和客戶興趣趨勢分析的整體原因。有時異常很容易識別並修正，例如購買 2,000 艘獨木舟的錯誤訂單。有時異常情況變得複雜，例如找出某一地區在特定時段內僅對特定定向行銷活動作出反應的趨勢。將跨量度的貢獻度項目與各個維度及其關聯組合起來，可以讓您全面了解客群互動，並對於異常資料點的背景有所了解。

以下提供一些使用案例：

* 藉由監控產品需求的變化，找出再行銷的潛力。
* 透過對特定受眾興趣做出反應來增強客戶體驗。
* 身分假性訂購，和界外報表一樣早。
* 保護您自己，藉由識別高使用量和下載，防止商業間諜行為。
* 監控作業，如報告遺失 JavaScript 標記。

全面分析異常後，會產生排名最前的項目的貢獻摘要，依發生總次數和項目的貢獻值百分比排序。已標準化的貢獻分數可讓您輕鬆比較和對比其他重要維度項目，並與之建立關聯。

## 貢獻度分析權杖

所有擁有貢獻度分析權限的客戶，每月可以在 Analysis Workspace 中執行完整的貢獻度分析但次數有限。貢獻度分析&#x200B;**不包括**&#x200B;點產品 (SiteCatalyst 15) 客戶、Analytics Foundation 客戶和 Analytics Select 客戶，這些客戶無權限使用貢獻度分析。

每家公司每月執行次數受到月度權杖數量的限制，而我們根據您的公司所購買的 Adobe Analytics 產品來授予權仗。每家公司執行次數的限制包括能夠限制貢獻度分析的存取權限，以避免權杖的濫用。

## 常見問題集

| 問題 | 回答 |
| --- | --- |
| 為什麼 Adobe 要推出代號？ | 「貢獻度分析」已成為 Adobe Analytics 中最能引起客戶共鳴的功能之一。每月提供少量的完整執行次數 (而不僅僅是某些 Analytics 產品的 3 個維度)，讓您可以了解無限制的完整貢獻度分析能為您帶來什麼。 |
| 在貢獻度分析中，權杖是如何運作的？使用現有的「貢獻分析」載入專案是否要扣除掉一個代號，或是在執行全新的「貢獻分析」時才需要這樣做？ | 每間登入公司 (非每位使用者) 每月都能取得特定數量的代號，讓您在 Analysis Workspace 中執行「完整」的貢獻分析。每次生成新的貢獻度分析時，您需要支付一個權杖。載入已執行過貢獻度分析的專案不會消耗權杖。 |
| 如果我的公司已用完權杖並想要執行額外的貢獻度分析，該怎麼辦？ | 您可以升級到其他 Adobe Analytics 產品，例如從標準版 (每月 2 個權杖) 升級到 Ultimate 版 (每月 20 個權杖)。您無法購買更多權杖。您必須在現有的封裝框架內進行升級。 |
| 我該如何限制對「貢獻分析」的存取權？ | 預設情況下，只有管理員有權執行貢獻分析。但是，管理員可以透過在 [Adobe Admin Console](/help/admin/admin-console/home.md) 中建立權限群組來授予存取權給其他使用者。唯有具備正當理由使用貢獻度分析並且值得信任不會濫用存取權限的使用者，才能獲得授予權限。此權限稱為「[!UICONTROL 貢獻分析]」，位於[!UICONTROL 報告套裝工具]下。[了解更多](/help/admin/admin-console/permissions/report-suite-tools.md) |
| 如何知道我的公司每月擁有多少個權杖，以及我的公司在當月已使用了多少個權杖？ | 請前往「[!UICONTROL 管理員] > [!UICONTROL 所有管理員] >[!UICONTROL 公司設定首頁] >[!UICONTROL 查看功能存取層級]」。 查看<ul><li>貢獻分析：每月使用代號數量</li><li>貢獻分析：本月使用代號數量</li></ul> |

## 異常偵測和貢獻分析權益

以下是 Analysis Workspace 中「異常偵測」和「貢獻分析」的詳細權益清单。

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adobe Analytics 權限 </th> 
   <th colname="col2" class="entry"> 異常偵測 </th> 
   <th colname="col3" class="entry"> 貢獻分析 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Foundation </p> </td> 
   <td colname="col2"> <p>只限每日顆粒度 </p> </td> 
   <td colname="col3" colsep="1"> <p>沒有權杖 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=B4XQ3X7G&amp;mv=other"  > Select </a> </p> </td> 
   <td colname="col2"> <p>只限每日顆粒度 </p> </td> 
   <td colname="col3"> <p>沒有權杖 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=91BF51TR&amp;mv=other"  >Prime</a> </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 10 個權杖 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 20 個權杖 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Predictive Workbench 附加元件 </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>無限量的權杖 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標準 </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics 核心 </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics：MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 2 個權杖 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (360，成效歸因) </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 2 個權杖 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (Complete、<a href="https://business.adobe.com/products/analytics/predictive-analytics.html"  >Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>無限量的權杖 </p> </td> 
  </tr> 
 </tbody> 
</table>
