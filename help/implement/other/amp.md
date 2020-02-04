---
title: 使用AMP實作
description: 在AMP頁面上實作Adobe Analytics。
translation-type: tm+mt
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# 使用AMP實作

[AMP](https://amp.dev) 是開放原始碼的HTML架構，提供直接的方式來建立快速順暢的網頁。

由於Adobe Analytics使用JavaScript程式庫來編譯和傳送影像要求，因此您的實作需要進行調整，才能在使用AMP的頁面上傳送資料至Adobe。

## 確定在使用AMP的頁面上實作Adobe Analytics的方法

Adobe已建立兩種方法來使用AMP在頁面上實作Adobe Analytics。 兩者都使用 `<amp-analytics>` HTML標籤。 如需 [詳細資訊，請參閱ampproject GitHub上的amp](https://github.com/ampproject/amphtml/tree/master/extensions/amp-analytics) -analytics標籤。

* **使用追`"adobeanalytics"`蹤範本**:直接在頁面上建構Analytics請求
* **使用追`"analytics_nativeConfig"`蹤範本**:使用包含您在一般網站上部署之相同AppMeasurement代碼的iframe

下表比較了這兩種方法：

|  | **「adobeanalytics」範本** | **「adobeanalytics_nativeConfig」範本** |
|---|---|---|
| 現有報表套裝中的訪客／瀏覽計數 | 高度膨脹 | 最小膨脹 |
| 使用個別的報表套裝 | 建議 | 非必要 |
| 全新 vs. 回頭的訪客 | 不支援 | 支援 |
| 訪客 ID 服務 | 不支援 | 支援 |
| 視訊和連結追蹤 | 部分支援 | 尚未支援 |
| 實施困難 | 有些困難 | 相對容易 |
| Adobe Experience cloud整合 | 不支援 | 部分支援 |

權衡組織內的利弊，以決定您要使用的方法。 如需 [范常式式碼](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web) ，請參閱Adobe GitHub儲存庫上的AMP範例。

> [!WARNING] 請勿使用AMP在同 `"adobeanalytics"` 一頁 `"adobeanalytics_nativeConfig"` 上同時使用和範本。 如果您嘗試這麼做，可以在瀏覽器主控台中產生錯誤，並重複計算訪客。

## 方法1:搭配「adobeanalytics」範本使用amp-analytics標籤

The `"adobeanalytics"` tracking template uses the `<amp-analytics>` HTML tag to construct a tracking request directly. 您可以指定在特定頁面事件上觸發的點擊請求，例如顯示頁面或點按。 點擊事件可以量身打造，明確指定選取器，以適用於特定元素 ID 或等級。您可以將 `type="adobeanalytics"` 新增到 amp-analytics 標籤以載入範本。

在以下的程式碼範例中，有兩個已定義的觸發器: `pageLoad` 和 `click`。當文 `pageLoad` 件變為可見時，觸發器就會觸發，並包 `pageName` 含區段中定義的變 `vars` 數。 The second trigger `click` fires when a button is clicked. `eVar1` 為此事件設定值 `button clicked`。

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.sc.omtrdc.net",
        "reportSuites": "reportSuiteID",
        "pageName": "Adobe Analytics Using amp-analytics tag"
      },
      "triggers": {
        "pageLoad": {
          "on": "visible",
          "request": "pageView"
        },
        "click": {
          "on": "click",
          "selector": "button",
          "request": "myClick",
          "vars": {
            "eVar1": "button clicked"
          }
        }
      }
    }
  </script>
</amp-analytics>
```

In the `click` trigger, you can specify a selector to ensure that whenever the specific DOM element is clicked (in this case, any button), the `buttonClick` request is fired and is automatically set to denote this hit as a link tracking call.

此外，`amp-analytics` 也支援一些變數替代，讓 AMP 能提供已知的資料數值。如需 [詳細資訊，請參閱GitHub上的amp-analytics](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) 支援的變數。

> [!NOTE] 使用此方法傳送至Adobe的影像要求不包含許多預設報表的資料（例如瀏覽器、螢幕大小或反向連結）。 如果您想在點擊中包含此資訊，請確定這些資訊是包含在影像請求查詢字串中。 如需詳細資訊，請參閱[資料收集查詢參數](../validate/query-parameters.md)。

Adobe使用內建的AMP函式識別訪客，並設定Cookie `adobe_amp_id`。 此訪客ID對Adobe Analytics設定的任何其他ID(例如 `s_vi` Cookie)都是唯一的。 使用此實作方法不支援Adobe Experience Cloud ID服務。

> [!NOTE] AMP使用CDN來傳送內容。 其結構化為計算訪客從中擷取內容的每個CDN的不同獨特訪客，而這會誇大獨特訪客計數。

由於AMP如何識別獨特訪客，因此建議對AMP頁面使用個別報表套裝。

This solution requires that the tracking server you specify in the `host` property matches the tracking server on your main site, so that your existing privacy policy controls are respected. 否則，請使用AMP為頁面建立個別的隱私權政策。

## 方法2:搭配「adobeanalytics_nativeConfig」範本使用amp-analytics標籤

The `"adobeanalytics_nativeConfig"` tag is easier to implement, as it uses the same tagging methodology you use on your normal web pages. 將下列項目新增至您的 `amp-analytics` 標籤：

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.sc.omtrdc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

您也需要網頁伺服器上裝載的HTML頁面：

```html
<html>
  <head>
    <title>Stats Example</title>
    <script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script>
    <script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script>
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
      s.visitorNamespace = s_visitorNamespace;
      s.visitor = visitor;
      s.pageName = s.Util.getQueryParam("pageName");
      s.eVar1 = s.Util.getQueryParam("v1");
      s.campaign = s.Util.getQueryParam("campaign");
      s.pageURL = s.Util.getQueryParam("pageURL");
      s.referrer = s.Util.getQueryParam("ref");
      s.t();
    </script>
  </body>
</html>
```

This approach sends data to a utility web page through query string parameters added to the `iframeMessage` request parameter. These query string parameters can be named whatever you like, as long as your `stats.html` page is configured to collect data from them.

`"adobeanalytics_nativeConfig"` 範本也根據列於 amp-analytics 標記的 `extraUrlParams` 區段變數，新增查詢字串參數。在上例中，包括 `pageName` 和 `v1` 參數。

> [!IMPORTANT] 您 `stats.html` 的頁面必須托管於AMP本身托管的網域以外的個別子網域上。 AMP 架構不允許來自與 AMP 本身存在網域相同之子網域的  iframe。例如，如果您的AMP代管於 `amp.example.com`，請將頁 `stats.html` 面托管於個別子網域，例如 `ampmetrics.example.com`。

使用此方法時，如果使用者在您的主要網站上退出追蹤，他們也會選擇不在您的所有AMP上追蹤。 使用此公用程式頁面也表示AMP可支援Adobe Experience Cloud ID服務。 不需要個別的報表套裝。

連結追蹤和視訊追蹤無法與此方法搭配使用。 AMP `iframeMessage` 中的標籤每頁只能載入一次，因此在影格載入後，您無法傳送任何其他影像要求。 此方法也需要執行更多的處理資源，這會影響捲動效能。 此方法不會影響頁面載入時間，因為所有資源會以非同步方式載入。

## 常見問題解答

**視訊追蹤是否適用於任一方法？**

不可以。AMP標準僅支援「可見」、「按一下」和「計時器」的觸發器。 它尚未支援標籤可監聽的視訊追蹤 `amp-analytics` 明確觸發器。 此外，范 `"adobeanalytics_nativeConfig"` 本只能載入一次，因此無法在頁面載入後繼續要求影像。

**如何在資料中區分AMP訪客與其他訪客？**

對於所有AMP頁面， [!UICONTROL JavaScript版本維度會收集類似的值]`AMP vX.X`。 您也可以將自訂維度設為&#39;AMP&#39;，以便區隔這些訪客。

**此實作方法與Facebook即時文章有何不同？**

Facebook即時文章支援與方法類似的解決 `"adobeanalytics_nativeConfig"` 方案。 此方 `stats.html` 法的頁面可同時滿足您對AMP和FIA的分析需求。 如需在FIA上實作追蹤的詳細資訊，請參閱 [Facebook即時文章](fb-instant-articles.md)。
