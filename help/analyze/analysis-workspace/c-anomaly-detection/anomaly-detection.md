---
description: 瞭解如何在Analysis Workspace中根據內容檢視和分析資料異常。
title: 異常偵測概觀
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: d37fa0aff0b1bbe196b943bc26e86b1e79936184
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 68%

---

# 異常偵測概觀

您可以在 Analysis Workspace 中根據內容檢視和分析資料異常。貢獻分析會與異常偵測搭配使用，協助識別造成異常的原因。


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [異常偵測](https://video.tv.adobe.com/v/25444?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Adobe Analytics Select與Adobe Analytics Foundation客戶在Workspace中只能存取&#x200B;*每日精細度*&#x200B;異常偵測。 如需更多資訊，請參閱[異常偵測和貢獻分析使用權限](#anomaly-detection-and-contribution-analysis-entitlements)。

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

異常偵測和[貢獻分析](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/anomaly-detection/anomaly-detection)是 Analysis Workspace 的核心工作流程。您可以對任何每日異常情形執行貢獻分析，並將結果內嵌至 Analysis Workspace 專案。

Analysis Workspace 異常偵測的演算法包含

* 除了現有的每日詳細程度，另支援對每小時、每週和每月的詳細程度。
* 感知季節性 (例如「黑色星期五」) 和假日。

## 貢獻分析

貢獻分析會探索您資料中的隱藏模式，以說明統計異常並識別背後的關聯

* 非預期的客戶動作，
* 界外值，以及
* 突然尖峰或下降

會聚受眾區段間所選量度的差異。


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [貢獻分析](https://video.tv.adobe.com/v/25443?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


發生異常。原因為何？異常偵測報表顯示訂購中有不尋常的尖峰，您想知道為什麼。發生什麼反常的事？誰正在回應哪個促銷活動或轉接？中毒了嗎？什麼特定因素造成這個異常現象？而最重要的可能是：我如何獲取有關客戶的重要資訊，並重複這表現？(或者，如果發生量度下降或是負量度上升，我日後要如何避免？)

貢獻分析能幫助您立即評估資料，解答異常為何發生。過去得耗費數週，現在只要幾秒鐘便能將異常貢獻劃分出來，提供讀者區段的模式，協助您發展出客戶互動的敘述。您可以策略性地運用貢獻分析，以識別並擷取有意義的關聯。 然後策略性地使用這些關聯來開發新的受眾區段，或策略性地識別觸發警報的界外或欺詐活動。

[異常偵測](#anomaly-detection)可根據選取的量度和選取的客群細分群體識別資料尖峰和極端的統計下降。異常偵測會根據培訓期間設定歷史基準，然後繪製與特定事件相互關聯的極度位移。 異常偵測可擷取「貢獻分析」要評估的統計相關資料點，報告正「訂購」量度中的陡峭上升、或負「彈回數」量度中的上升、或是這兩者中的下降。 一旦識別統計異常，貢獻分析可讓您針對所有異常資料點深入鑽研，並評估相關的行銷和促銷活動變數。它會執行進階演算和機器學習程序，評估重要尖峰或下降的貢獻因素的關聯性。這些計算接著會透過互動式視覺效果的方式顯示，為您提供各種不同觀點，以便了解發生特定現象的原因，以及因應的方式。

「貢獻分析」可協助您發展敘述，以說明異常發生的原因。 以及如何回應異常、擷取相關量度並識別隱藏點，為您提供對象互動和趨勢客戶興趣的整體原因。 有時候異常很容易看出來及更正，例如 2,000 艘小艇的錯誤訂購。有時候就很複雜，像是識別某地區某時段只對特定目標促銷活動有反應的新興趨勢。將不同維度之量度及其關聯的貢獻項目組合在一起，可以給您讀者互動的整體概念，並協助提供異常資料點的內容。

以下提供一些使用案例：

* 藉由監控產品需求的變化，找出再行銷的潛力。
* 透過對特定受眾興趣做出反應來增強客戶體驗。
* 身分假性訂購，和界外報表一樣早。
* 保護您自己，藉由識別高使用量和下載，防止商業間諜行為。
* 監控作業，例如報告遺失JavaScript標籤。

全面分析異常後，會產生排名最前的項目的貢獻摘要，依發生總次數和項目的貢獻值百分比排序。已標準化的貢獻分數可讓您輕鬆比較和對比其他重要維度項目，並與之建立關聯。

## 貢獻分析代號

具有「貢獻分析」使用權限的所有客戶可以在 Analysis Workspace 中，每月以有限次數執行完整的「貢獻分析」。貢獻分析&#x200B;**不包括**&#x200B;點產品(SiteCatalyst 15)客戶、Analytics Foundation客戶和Analytics Select客戶，這些客戶無權使用「貢獻分析」。

每間公司的執行次數，會根據貴公司購買的 Adobe Analytics 產品所授予的權限，受到每月代號數的限制。每個公司的執行次數包含限制「貢獻分析」存取權的功能，以避免權杖濫用。

## 常見問題集

| 問題 | 回答 |
| --- | --- |
| 為什麼 Adobe 要推出代號？ | 「貢獻分析」已成為 Adobe Analytics 中迴響最熱烈的功能之一。您每月皆可執行小量的完整分析（而非只有部分Analytics產品的3個維度），因此能夠瞭解完整不受限的「貢獻分析」所能提供的功能。 |
| 代號如何在「貢獻分析」中運作？ 使用現有的「貢獻分析」載入專案是否要扣除掉一個代號，或是在執行全新的「貢獻分析」時才需要這樣做？ | 每間登入公司 (非每位使用者) 每月都能取得特定數量的代號，讓您在 Analysis Workspace 中執行「完整」的貢獻分析。您每次產生一個新的貢獻分析，就要支付一個代號。使用預先執行的「貢獻分析」載入專案並不需要扣除代號。 |
| 如果我的公司用完代號，但想要執行更多「貢獻分析」，該怎麼做？ | 您可以升級至其他 Adobe Analytics 產品，例如從 Standard (每月 2 個代號) 升級為 Ultimate (每月 20 個代號)。您無法購買更多代號。 您必須在現有的封裝架構中升級。 |
| 我該如何限制對「貢獻分析」的存取權？ | 預設情況下，只有管理員有權執行貢獻分析。但是，管理員可以透過在 [Adobe Admin Console](https://experienceleague.adobe.com/zh-hant/docs/analytics/admin/admin-console/home) 中建立權限群組來授予存取權給其他使用者。只有具備正當理由使用貢獻分析，且相信不會濫用存取權的使用者，才有權使用貢獻分析。 此權限稱為「[!UICONTROL 貢獻分析]」，位於[!UICONTROL 報告套裝工具]下。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics/admin/admin-console/permissions/report-suite-tools) |
| 我該如何得知敝公司每個月有權使用多少代號，以及敝公司當月已使用多少代號？ | 請前往「[!UICONTROL 管理員] > [!UICONTROL 所有管理員] >[!UICONTROL 公司設定首頁] >[!UICONTROL 查看功能存取層級]」。 查看<ul><li>貢獻分析：每月使用代號數量</li><li>貢獻分析：本月使用代號數量</li></ul> |

## 異常偵測和貢獻分析權益

以下是 Analysis Workspace 中「異常偵測」和「貢獻分析」的詳細權益清单。

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
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=B4XQ3X7G&amp;mv=other"  > Select </a> </p> </td> 
   <td colname="col2"> <p>僅每日粒度 </p> </td> 
   <td colname="col3"> <p>沒有代號 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=91BF51TR&amp;mv=other"  >Prime</a> </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 10 個代號 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 20 個代號 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Predictive Workbench附加元件 </p> </td> 
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
   <td colname="col1"> <p>Premium (Complete、<a href="https://business.adobe.com/products/analytics/predictive-analytics.html"  >Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>代號数量不受限制 </p> </td> 
  </tr> 
 </tbody> 
</table>
