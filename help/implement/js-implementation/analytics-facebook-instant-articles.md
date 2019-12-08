---
description: 如何在 Facebook 即時文章中實施。
keywords: Analytics Implementation;embed;custom variable;custom event;visitor tracking;tracking;limitations
title: Facebook 即時文章
topic: Developer and implementation
uuid: 04b6366b-7c52-4dae-b2dd-bb6b78fd409c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Facebook 即時文章

如何在 Facebook 即時文章中實施。

Facebook 即時文章 是出版業者在Facebook上建立快速互動文章的新方法。 即時文章載入內容的速度快達行動網路的十倍。

Adobe Analytics 可以內嵌於 Facebook 即時文章，於訪客與內容互動時追蹤其行為。由於發佈者的內容發佈於 Facebook 應用程式內，而非發佈者的網站，則標記方法與標準 Analytics 實施略有不同。

## 步驟 1.內嵌 Analytics HTML 頁面 {#section_0DF847F8BA624CF8A239C10003A39E59}

您在創建 Facebook 即時文章內容時，可以將 HTML 內容內嵌於  iFrame 中。例如:

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html" height="0"></iframe>
```

## 步驟 2.修改您的 Analytics HTML {#section_76707B51D63A47FF833C2D3FFF8412B4}

以下的 HTML 樣本可以用於擷取即時文章的數據。此檔案會託管於貴公司其中一部網路伺服器。每次載入即時文章時，也會以步驟一之方法在 iframe 中載入該檔案，而此會觸發傳送分析資料至 Adobe。

```
<html> 
    <head> 
        <title>Facebook Stats</title> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/VisitorAPI.js"></script> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/AppMeasurement.js"></script> 
    </head> 
    <body> 
        <script> 
            //Standard Variable Configuration 
   var v_orgId = "[your-marketing-cloud-org-id]@AdobeOrg"; 
   var s_account = "[your-report-suite-id]"; 
   var s_trackingServer = "[your-tracking-server]"; 
   var s_visitorNamespace = "[your-namespace]"; 
     
   //Instantiation 
   var visitor = Visitor.getInstance(v_orgId); 
   visitor.trackingServer = s_trackingServer; 
     
   var s = s_gi(s_account); 
   s.account = s_account; 
   s.trackingServer = s_trackingServer; 
   s.visitorNamespace = s_visitorNamespace; 
   s.visitor = visitor; 
     
   //Custom Variables 
   s.pageName = s.Util.getQueryParam("pageName"); 
   s.prop10 = "Facebook Instant Article"; 
       
   //Page View Image Request Call 
   s.t(); 
        </script> 
    </body> 
</html> 
```

**若要修改此樣本 HTML 以供您特定實施**

1. 建議您將未修改過的 VisitorAPI.js 及 AppMeasurement.js 版本最新複本託管於貴公司網路伺服器上的一般資料夾。

   若有需要，這些檔案也可以從 Analytics UI 的程式碼管理員中下載。

1. 將以下項目納入您的 Analytics 實施標準設定變數:

   1. 您的 Experience Cloud 組織 ID。
   1. 可擷取 Facebook 即時文章流量的報表套裝 ID。
   1. 貴公司的追蹤伺服器網域。
   1. 您的訪客命名空間變數。**請注意:** 您的標準 Analytics 實施中可找到許多此類數值。若有需要，客戶服務或 Adobe 諮詢可以協助提供適當的數值。

1. [設定自訂變數及事件追蹤](/help/implement/js-implementation/analytics-facebook-instant-articles.md#section_932C41BD21154C25B99389299BDF3E0B).
1. 納入頁面檢視影像要求語法 `( s.t())`。

## 步驟 3.設定自訂變數及事件追蹤 {#section_932C41BD21154C25B99389299BDF3E0B}

自訂變數及事件可經由不同方法，於您的分析 HTML 追蹤。第一種方法是在您自訂的設定中納入 JavaScript 邏輯，此與您在標準 Analytics 實施中所為相似。例如，要設定 prop 的數值，只要簡單使用您於一般實施中使用的語法即可。

```
s.prop10 = "Facebook Instant Article";
```

您也可以充分利用 iframe `src` 歸因中的查詢字串參數，以用動態方式將變數傳送至 iframe。例如:

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html?prop1=dynamic%20article%20title&eVar1=facebook%20page%20name&pageName=your%20page%20name%20here&cmpId=your%20campaignID%20here" height="0"></iframe>
```

若接著要於您的分析 HTML JavaScript 中的自訂變數區域設定這些查詢字串參數，請使用預設的 程式庫中的 `Util.getQueryParam`[!DNL AppMeasurement] 函數，如下所示:

```
s.pageName = s.Util.getQueryParam("pageName"); 
s.campaign = s.Util.getQueryParam("cmpId"); 
s.eVar1 = s.Util.getQueryParam("eVar1"); 
s.prop1 = s.Util.getQueryParam("prop1"); 
```

## 訪客追蹤 {#section_60F0C77659534949831E85B5FD9AE81E}

只要 Analytics HTML 頁面託管於您的網路伺服器，Adobe 都能透過 Facebook 即時文章支援您現有的隱私政策。此表示，若使用者選擇拒絕您在原始網站中的追蹤，使用者也可以選擇拒絕所有您在 Facebook 即時文章中的追蹤，且不需要額外步驟。使用此公用程式網頁也表示支援 Identity 服務 (訪客 ID)，讓您能整合自 Facebook 即時文章擷取的量度及變數與其餘的 Experience Cloud 功能。(針對目標廣告則以 [!DNL Adobe Audience Manager] 為例)。

## 追蹤限制 {#section_1EE1BB069A3148DB9446371AFE196567}

此方法本身有幾個問題。任何只能在 Facebook 即時文章上經由 JavaScript 取得的 DOM 數值 (如反向連結)，在追蹤過程中都無法於 iframe 取得。然而，標準技術報告如瀏覽器、裝置、螢幕大小或解析度應會正常運作。此外，自您的公用程式網頁參考 [!DNL document.referrer]，可取得 pageURL。

## 接下來還有什麼? {#section_A170A10E2A3642A784DF720195DA8B38}

[!DNL Adobe Analytics] 對於與 Facebook 及我們的發佈者合作興致勃勃，期待於行動網路將業界領先的分析功能帶給發佈者，提供超凡的高速使用者體驗。我們仍致力於建立最佳的長期解決方案，以回應客戶不斷改變的分析需求。

Facebook 即時文章專案正快速發展並隨時變更，請您經常與我們聯繫，取得更新資訊。隨著我們進一步改善整合方式，以及將來採用 Facebook 即時文章的發佈者人數增加，請期待我們將做出更多變更。

若您有問題或疑問，請聯繫您的 Adobe 顧問或客戶服務。
