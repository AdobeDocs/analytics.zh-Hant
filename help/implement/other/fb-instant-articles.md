---
title: 使用Facebook即時文章實作
description: 在Facebook即時文章頁面上實作Adobe Analytics。
translation-type: tm+mt
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# 使用Facebook即時文章實作

Facebook Instant Articles可讓出版業者在Facebook上建立快速的互動文章。 即時文章載入內容的速度快達行動網路的十倍。

您可以將Adobe Analytics內嵌在Facebook即時文章中，以追蹤訪客行為。 由於發行者內容位於Facebook應用程式內，而非發佈者網站上，因此標籤方法與標準Analytics實作稍有不同。

## 工作流程

實作Adobe Analytics的主要工作流程如下：

1. 建立頁 `stats.html` 面。 請撰寫此頁面的程式碼，以從URL提取查詢字串參數，並將每個參數指派給Analytics變數
1. 在您的網 `stats.html` 頁伺服器上代管頁面
1. 在Facebook即時文章上實作分析，方法是參照iframe `stats.html` 中的檔案
1. 在iframe屬性中包含查詢字串參 `src` 數

### 步驟1:建立頁 `stats.html` 面

以下的 HTML 樣本可以用於擷取即時文章的數據。此檔案會託管於貴公司其中一部網路伺服器。每次載入「即時文章」時，都會將檔案載入iframe中，這會觸發傳送資料至Adobe。

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
      var s_account = "examplersid";
      var s_trackingServer = "example.sc.omtrdc.net";
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

### 步驟2:在您的網 `stats.html` 頁伺服器上代管頁面

Adobe建議將您的頁 `stats.html` 面與最新版本的和 `AppMeasurement.js` 一起 `VisitorAPI.js`代管。 與組織中適當的工程團隊合作，將此檔案存放在正確的位置。

### 步驟3:每個Facebook `stats.html` 即時文章頁面上的參考

建立Facebook即時文章內容時，請將分析HTML內容內嵌在iframe中。 例如:

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### 步驟4:設定自訂變數和事件追蹤

您可以透過兩種不同的方法，在分析HTML中追蹤自訂變數和事件：

* 直接在頁面中包含變數值和 `stats.html` 事件。 此處定義的變數最適合所有Facebook即時文章通常相同的值。
* 將變數值納入參考iframe的查詢字串。 此方法可讓您將變數值從Facebook即時文章傳送至裝載Analytics代碼的iframe。

下列範例顯示查詢字串中包含的數個自訂變數。 然後，內部的JavaScript `stats.html` 會使用檢查查詢字串 `s.Util.getQueryParam()`。

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

> [!NOTE] 由於iframe的性質，「反向連結」維度不會自動追蹤。 如果您想要追蹤此維度，請務必將此維度加入查詢字串中。

## Facebook即時文章與隱私權

只要Analytics HTML頁面是裝載在您的網頁伺服器上，Adobe就會支援您所有Facebook即時文章的現有隱私權政策。 如果使用者選擇退出您主要網站上的追蹤，他們也會選擇退出您所有Facebook即時文章上的追蹤。 此公用程式頁面也支援Adobe Experience Cloud Identity Service，讓您可以將Facebook即時文章資料與Experience cloud的其他部分整合。
