---
description: 您可以在 Analysis Workspace 中根據內容檢視和分析資料異常。
title: 異常偵測概述
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: ht
source-wordcount: '1402'
ht-degree: 100%

---

# 異常偵測概述

您可以在 Analysis Workspace 中根據內容檢視和分析資料異常。貢獻分析與異常檢測結合使用，協助識別導致異常的原因。

>[!VIDEO](https://video.tv.adobe.com/v/25444/?quality=12)

>[!IMPORTANT]
>
>Adobe Analytics Select 與 Adobe Analytics Foundation 客戶在工作區中只能存取「每日粒度」的異常偵測功能。如需更多資訊，請參閱[異常偵測和貢獻分析使用權限](#anomaly-detection-and-contribution-analysis-entitlements)。

## 異常偵測

「異常偵測」提供一種統計方法，以判斷指定的量度和先前的資料比較有何變更。

異常偵測可讓您區隔「真實訊號」與「雜訊」，接著找出形成這些訊號或異常情形的可能因素。換句話說，可讓您識別哪些統計波動是重要的、哪些不重要。接著您可以找出真正異常的根本原因。此外，您還可以取得可靠的量度 (KPI) 預測。

您可能會調查的異常例子包括：

* 訂單平均值大幅下降
* 低收入訂單發生尖峰
* 試用版註冊發生尖峰或下降
* 登陸頁面檢視次數下降
* 影片緩衝事件的尖峰
* 低影片位元率的尖峰

異常偵測和[貢獻分析](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html)是 Analysis Workspace 的核心工作流程。您可以對任何每日異常情形執行貢獻分析，並將結果內嵌至 Analysis Workspace 專案。

Analysis Workspace 異常偵測的演算法包含

* 除了現有的每日詳細程度，另支援對每小時、每週和每月的詳細程度。
* 感知季節性 (例如「黑色星期五」) 和假日。

## 貢獻分析

貢獻分析會探索您資料中的隱藏模式，說明統計異常並識別聚合讀者區段間非預期客戶動作、界外值、選定量度突升或突降背後的關聯。

>[!VIDEO](https://video.tv.adobe.com/v/25443/?quality=12)

發生異常。原因為何？異常偵測報表顯示訂購中有不尋常的尖峰，您想知道為什麼。發生什麼反常的事？誰正在回應哪個促銷活動或轉接？中毒了嗎？什麼特定因素造成這個異常現象？而最重要的可能是：我如何獲取有關客戶的重要資訊，並重複這表現？(或者，如果發生量度下降或是負量度上升，我日後要如何避免？)

貢獻分析能幫助您立即評估資料，解答異常為何發生。過去得耗費數週，現在只要幾秒鐘便能將異常貢獻劃分出來，提供讀者區段的模式，協助您發展出客戶互動的敘述。您可以策略性地利用貢獻分析來識別及擷取有意義的關聯以開發新的讀者區段，或高明地運用它識別出觸發警示的界外或假性活動。

[異常偵測](#anomaly-detection)可根據選取的量度和選取的讀者區段識別資料尖峰和極端的統計下降。它依據培訓期間設定歷史基準，然後繪製與特定事件相互關聯的極度偏移。它可以擷取「貢獻分析」要評估的統計相關資料點，報表正面量度「訂購」中的陡峭上升、或負面量度「彈回數」中的上升、或是這兩者中的下降。一旦識別統計異常，貢獻分析可讓您針對所有異常資料點深入鑽研，並評估相關的行銷和促銷活動變數。它會執行進階演算和機器學習程序，評估重要尖峰或下降的貢獻因素的關聯性。這些計算接著會顯示在互動視覺效果中，這些視覺效果可提供您各種不同觀點，以便了解某些現象為何發生，以及如何做出對應。

「貢獻分析」幫助您發展出敘述，描述異常為何發生及如何回應，可擷取相關量度並識別隱藏點，提供您讀者互動與客戶興趣趨勢的總體原因。有時候異常很容易看出來及更正，例如 2,000 艘小艇的錯誤訂購。有時候就很複雜，像是識別某地區某時段只對特定目標促銷活動有反應的新興趨勢。將不同維度之量度及其關聯的貢獻項目組合在一起，可以給您讀者互動的整體概念，並協助提供異常資料點的內容。

以下提供一些使用案例：

* 藉由監控產品需求的變化，找出再行銷的潛力。
* 提升客戶體驗，方式是透過對特定讀者興趣有所反應。
* 身分假性訂購，和界外報表一樣早。
* 保護您自己，藉由識別高使用量和下載，防止商業間諜行為。
* 監控作業，如報告遺失 javascript 標記。

全面分析異常後，會產生排名最前的項目的貢獻摘要，依發生總次數和項目的貢獻值百分比排序。已標準化的貢獻分數可讓您輕鬆比較和對比其他重要維度項目，並與之建立關聯。

## 貢獻分析代號 - 概觀 {#section_3EF8D2BBCE6E4C309D753BCF04A453D0}

>[!IMPORTANT]
>
>「貢獻分析」已從 Reports &amp; Analytics 功能集中移除，現在只能透過 Analysis Workspace 使用。

具有「貢獻分析」使用權限的所有客戶可以在 Analysis Workspace 中，每月以有限次數執行完整的「貢獻分析」。惟單點產品 (SiteCatalyst 15) 客戶、Analytics Foundation 客戶及 Analytics Select 客戶&#x200B;**除外**，因為他們沒有取得「貢獻分析」功能。

每間公司的執行次數，會根據貴公司購買的 Adobe Analytics 產品所授予的權限，受到每月代號數的限制。此外還包括是否能限制「貢獻分析」的存取權，避免他人誤用代號。

## 常見問題集 {#section_11D0431AD2014B96AB9561CA66A367CE}

| 問題 | 回答 |
| --- | --- |
| 為什麼 Adobe 要推出代號？ | 「貢獻分析」已成為 Adobe Analytics 中迴響最熱烈的功能之一。您每月皆可執行小量的「完整」分析 (而非只有部分 Analytics 產品的 3 個維度)，因此能夠更加了解完整不受限的「貢獻分析」所能提供的功能。 |
| 代號如何在「貢獻分析」中運作？ 使用現有的「貢獻分析」載入專案是否要扣除掉一個代號，或是在執行全新的「貢獻分析」時才需要這樣做？ | 每間登入公司 (非每位使用者) 每月都能取得特定數量的代號，讓您在 Analysis Workspace 中執行「完整」的貢獻分析。您每次產生一個新的貢獻分析，就要支付一個代號。使用預先執行的「貢獻分析」載入專案並不需要扣除代號。 |
| 代號適用於 Reports &amp; Analytics 中的「貢獻分析」嗎？ | 不可以， 自 2018 年 4 月起，Reports &amp; Analytics 中不再提供「貢獻分析」。 |
| 如果我的公司用完代號，但想要執行更多「貢獻分析」，該怎麼做？ | 您可以升級至其他 Adobe Analytics 產品，例如從 Standard (每月 2 個代號) 升級為 Ultimate (每月 20 個代號)。您無法單純購買更多代號，您必須在現有的封包框架內升級。 |
| 我該如何限制對「貢獻分析」的存取權？ | 預設情況下，只有管理員有權執行貢獻分析。但是，管理員可以透過在 [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=zh-Hant) 中建立權限群組來授予存取權給其他使用者。您必須確認使用者具備正當理由，且不會濫用存取權，才可將使用貢獻分析的權限授予對方。此權限稱為「[!UICONTROL 貢獻分析]」，位於[!UICONTROL 報告套裝工具]下。[了解更多](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/report-suite-tools.html?lang=zh-Hant) |
| 我該如何得知敝公司每個月有權使用多少代號，以及在當月中已使用的數量？ | 請前往「[!UICONTROL 管理員] > [!UICONTROL 所有管理員] >[!UICONTROL 公司設定首頁] >[!UICONTROL 查看功能存取層級]」。 查看<ul><li>貢獻分析：每月使用代號數量</li><li>貢獻分析：本月使用代號數量</li></ul> |

## 異常偵測和貢獻分析權益 {#section_9278D58F21A840AA9B1ED1BD07A1EF0A}

以下是 Analysis Workspace 中「異常偵測」和「貢獻分析」的詳細權益清单。

>[!IMPORTANT]
>
>「異常偵測」和「貢獻分析」這兩項功能已從 Reports &amp; Analytics 功能集中移除，現在只能透過 Analysis Workspace 使用。請注意，Adobe Analytics Select 與 Adobe Analytics Foundation 客戶在工作區中只能存取「每日粒度」的異常偵測功能。

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adobe Analytics 使用權限 </th> 
   <th colname="col2" class="entry"> 異常偵測 </th> 
   <th colname="col3" class="entry"> 貢獻分析 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Foundation </p> </td> 
   <td colname="col2"> <p>僅每日粒度 </p> </td> 
   <td colname="col3" colsep="1"> <p>沒有代號 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/tw/data-analytics-cloud/analytics/select.html?promoid=B4XQ3X7G&amp;mv=other"  > Select </a> </p> </td> 
   <td colname="col2"> <p>僅每日粒度 </p> </td> 
   <td colname="col3"> <p>沒有代號 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/tw/data-analytics-cloud/analytics/prime.html?promoid=91BF51TR&amp;mv=other"  >Prime</a> </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 10 個代號 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/tw/data-analytics-cloud/analytics/ultimate.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 20 個代號 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>+Predictive Workbench </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>代號数量不受限制 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標準 </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics：MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 2 個代號 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (360、Attribution) </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 2 個代號 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (Complete、<a href="https://www.adobe.com/tw/data-analytics-cloud/analytics/predictive-intelligence.html"  >Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>代號数量不受限制 </p> </td> 
  </tr> 
 </tbody> 
</table>
