---
title: 使用 Facebook 即時文章進行實施
description: 在 Facebook 即時文章頁面上實施 Adobe Analytics。
feature: Implementation Basics
exl-id: 2189f70d-32f0-4137-9d53-7acab0f15e6c
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 100%

---

# 使用 Facebook 即時文章進行實施

Facebook 即時文章可讓發佈者於 Facebook 上快速建立互動式文章。即時文章載入內容的速度快達行動網路的十倍。

您可以將 Adobe Analytics 嵌入在 Facebook 即時文章中，藉此追蹤訪客行為。由於發佈者的內容發佈於 Facebook 應用程式內，而非發佈者的網站，則標記方法與標準 Analytics 實施略有不同。

## 工作流程

實施 Adobe Analytics 的整體工作流程如下：

1. 建立 `stats.html` 頁面。撰寫此頁面的程式碼，從 URL 提取查詢字串參數，並將每個參數指派給 Analytics 變數
1. 在您的 Web 伺服器上託管 `stats.html` 頁面
1. 參考 iframe `stats.html` 中的檔案，在 Facebook 即時文章上實施 Analytics
1. 在 iframe `src` 屬性中包含查詢字串參數

### 步驟1：建立 `stats.html` 頁面

以下的 HTML 樣本可以用於擷取即時文章的數據。此檔案會託管於貴公司其中一部網路伺服器。每次載入即時文章時，都會在 iframe 中載入檔案，進而觸發將資料傳送至 Adobe。

```html
<html>
  <head>
    <title>Facebook Stats</title>
      <script language="javaScript" type="text/javascript" src="VisitorAPI.js"></script>
      <script language="javaScript" type="text/javascript" src="AppMeasurement.js"></script>
  </head>
  <body>
    <script>
      var v_orgId = "INSERT-ORG-ID-HERE";
      var s_account = "examplersid1,examplersid2";
      var s_trackingServer = "example.data.adobedc.net";
      var visitor = Visitor.getInstance(v_orgId);
      visitor.trackingServer = s_trackingServer;

      var s = s_gi(s_account);
      s.account = s_account;
      s.trackingServer = s_trackingServer;
      s.visitor = visitor;

      s.pageName = s.Util.getQueryParam("pageName");
      s.pageURL = document.referrer; // The referrer to the utility page is the parent frame
      s.campaign = s.Util.getQueryParam("cmpId");
      s.eVar1 = "Facebook Instant Article";
      s.eVar2 = s.Util.getQueryParam("eVar2");

      s.t();
    </script>
  </body>
</html>
```

### 步驟 2：在您的 Web 伺服器上託管 `stats.html` 頁面

Adobe 建議將您的 `stats.html` 頁面與最新版本的 `AppMeasurement.js` 和 `VisitorAPI.js` 一起託管。與貴組織的適當工程團隊合作，在正確的位置託管此檔案。

### 步驟 3：參考每個 Facebook 即時文章頁面上的 `stats.html`

建立 Facebook 即時文章內容時，可以將 HTML 內容嵌入於 iframe 中。例如：

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### 步驟 4：設定自訂變數及事件追蹤

可於您的分析 HTML 中經由兩種方法追蹤自訂變數及事件：

* 直接在 `stats.html` 頁面中包含變數值和事件。此處定義的變數最適合所有 Facebook 即時文章通常相同的值。
* 將變數值加入參考 iframe 的查詢字串中。此方法可讓您將變數值從 Facebook 即時文章傳送至託管 Analytics 程式碼的 iframe。

下列範例顯示查詢字串中包含的多個自訂變數。接著 `stats.html` 內的 JavaScript 會使用 `s.Util.getQueryParam()` 來檢查查詢字串。

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

>[!NOTE]
>
>由於 iframe 的性質，系統不會自動追蹤「反向連結」維度。如果您想要追蹤此維度，請務必將此維度加入查詢字串中。

## Facebook 即時文章與隱私權

只要 Analytics HTML 頁面託管於您的網路伺服器，Adobe 就會透過 Facebook 即時文章支援您現有的隱私權政策。若使用者選擇不追蹤您的主要網站，也會同時選擇不追蹤您所有的 Facebook 即時文章。此公用程式頁面也支援 Adobe Experience Cloud 身分識別服務，因此您可以將 Facebook 即時文章資料與 Experience Cloud 的其他部分整合。
