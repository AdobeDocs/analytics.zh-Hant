---
title: 使用 AMP 進行實施
description: 在 AMP 頁面上實施 Adobe Analytics。
translation-type: tm+mt
source-git-commit: 684e67203b2e3d5f0cb82cdbdda1f24d37a677f0
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 100%

---


# 使用 AMP 進行實施

[AMP](https://amp.dev) 是開放原始碼的 HTML 架構，提供簡單明瞭的方式，可建立快速且順暢載入的網頁。

由於 Adobe Analytics 使用 JavaScript 程式庫來編譯和傳送影像要求，因此您的實施需要進行調整，才能在使用 AMP 的頁面上將資料傳送至 Adobe。

## 決定要透過什麼方法在使用 AMP 的頁面上實施 Adobe Analytics

Adobe建立的兩種方法可使用 AMP 在頁面上實施 Adobe Analytics。兩者都使用 `<amp-analytics>` HTML 標籤。如需詳細資訊，請參閱 ampproject GitHub 上的 [amp -analytics 標籤](https://github.com/ampproject/amphtml/tree/master/extensions/amp-analytics)。

* **使用`"adobeanalytics"`追蹤範本**：直接在頁面上建立 Analytics 要求
* **使用`"analytics_nativeConfig"`追蹤範本**：使用 iframe，其中包含您部署在一般網站上的相同 AppMeasurement 程式碼。

下表比較這兩種方法：

|  | **「adobeanalytics」範本** | **「adobeanalytics_nativeConfig」範本** |
|---|---|---|
| 現有報表套裝中的訪客/造訪計數 | 高度膨脹 | 最小膨脹 |
| 使用個別報表套裝 | 建議 | 非必要 |
| 全新 vs. 回訪訪客 | 不支援 | 支援 |
| 訪客 ID 服務 | 不支援 | 支援 |
| 視訊和連結追蹤 | 部分支援 | 尚未支援 |
| 實施困難 | 有些困難 | 相對容易 |
| Adobe Experience Cloud 整合 | 不支援 | 部分支援 |

權衡組織內的優點與缺點，決定您要使用哪種方法。如需程式碼範例，請參閱 Adobe GitHub 儲存庫上的 [AMP 範例](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web)。

>[!WARNING]
>
>請勿在使用 AMP 的同一頁上同時使用 `"adobeanalytics"` 和 `"adobeanalytics_nativeConfig"` 範本。如果嘗試這麼做，可能會在瀏覽器主控台中產生錯誤，並重複計算訪客。

## 方法 1：透過「adobeanalytics」範本使用 amp-analytics 標籤

`"adobeanalytics"`追蹤範本使用 `<amp-analytics>` HTML 標籤直接建立追蹤要求。您可以指定在特定頁面事件上引發的點擊要求，例如頁面顯示或點按。點擊事件可以量身打造，明確指定選取器，以適用於特定元素 ID 或等級。您可以將 `type="adobeanalytics"` 新增到 amp-analytics 標籤以載入範本。

在以下的程式碼範例中，有兩個已定義的觸發器：`pageLoad` 和 `click`。文件變為可見時，`pageLoad` 觸發器就會引發，並包含 `pageName` 區段中定義的 `vars` 變數。第二個觸發器 `click` 則會於有人點按某按鈕時引發。使用值 `eVar1` 設定 `button clicked` 以用於此事件。

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
          "request": "pageview"
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

在 `click` 觸發器中，您可以指定一個選取器，確保每當有人點按特定 DOM 元素 (在此為任何按鈕)，`buttonClick` 要求都會引發，且會自動設為將此點擊表示為連結追蹤呼叫。

此外，`amp-analytics` 也支援一些變數替代，讓 AMP 能提供已知的資料數值。如需詳細資訊，請參閱 GitHub 上的 [amp-analytics 支援的變數](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md)。

>[!NOTE]
>
>使用此方法傳送至 Adobe 的影像要求不包含許多預設報表的資料 (例如瀏覽器、螢幕大小或反向連結)。如果您想在點擊中包含這些資訊，請確定這些資訊包含在影像要求查詢字串中。如需詳細資訊，請參閱[資料彙集查詢參數](../validate/query-parameters.md)。

Adobe 使用內建 AMP 函數來識別訪客，並設定 Cookie `adobe_amp_id`。此訪客 ID 與 Adobe Analytics 設定的任何其他 ID 均不重複 (例如 `s_vi` Cookie)。使用此實施方法不支援 Adobe Experience Cloud ID Service。

>[!NOTE]
>
>AMP 會使用 CDN 來傳送內容。CDN 的結構化會針對訪客從中擷取內容的每個 CDN 計算不同的不重複訪客，而這會誇大獨特訪客的計數。

考量到 AMP 識別獨特訪客的方式，建議對 AMP 頁面使用獨立的報表套裝。

此解決方案要求，您於 `host` 屬性中指定的追蹤伺服器需與您主要網站的追蹤伺服器一致，才能接受您現有的隱私權政策。若不一致，請使用 AMP 為頁面建立獨立的隱私權政策。

## 方法 2：透過「adobeanalytics_nativeConfig」範本使用 amp-analytics 標籤

`"adobeanalytics_nativeConfig"` 標籤讓實施變得更輕鬆，因為其使用的標記方法與您在一般網頁上使用的相同。將下列項目新增至您的 `amp-analytics` 標籤：

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

也需要在您 Web 伺服器上託管的 HTML 頁面：

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

此作法會透過新增至 `iframeMessage` 要求參數中的查詢字串參數，將資料傳送至公用程式網頁。只要您的 `stats.html` 頁面已設為從這些參數收集資料，您就可以隨意命名這些查詢字串參數。

`"adobeanalytics_nativeConfig"` 範本也根據列於 amp-analytics 標記的 `extraUrlParams` 區段變數，新增查詢字串參數。在上例中，納入了 `pageName` 和 `v1` 參數。

>[!IMPORTANT]
>
>您的 `stats.html` 頁面應託管於 AMP 本身託管網域的獨立子網域上。AMP 架構不允許來自與 AMP 本身存在網域相同之子網域的  iframe。舉例說明，若您的 AMP 託管於 `amp.example.com`，請將您的 `stats.html` 頁面託管於獨立的子網域上，例如 `ampmetrics.example.com`。

使用此方法時，若使用者選擇不追蹤您的主要網站，也會同時選擇不追蹤您所有的 AMP。使用此公用程式頁面也表示 AMP 可支援 Adobe Experience Cloud ID Service。不需要獨立的報表套裝。

連結追蹤和視訊追蹤無法搭配此方法使用。AMP 中的 `iframeMessage` 標籤每頁只能載入一次，因此影格載入後，就無法傳送其他任何影像要求。此方法也需要執行更多處理資源，而這會影響捲動效能。此方法不會影響頁面載入時間，因為所有資源都以非同步方式載入。

## 常見問題集

**視訊追蹤是否適用於任一種方法？**

不可以。AMP 標準僅支援「可見」、「點按」和「計時器」的觸發器。尚不支援標籤可監聽 `amp-analytics` 標籤的視訊追蹤明確觸發器。此外，`"adobeanalytics_nativeConfig"` 範本只能載入一次，因此頁面載入後就無法傳送後續要求影像。

**如何在資料中區分 AMP 訪客與其他訪客？**

對於所有 AMP 頁面，[!UICONTROL JavaScript 版本]維度會收集類似 `AMP vX.X` 的值。您也可以將自訂維度設為「AMP」以便區隔這些訪客。

**此實施方法與 Facebook 即時文章有何不同？**

Facebook 即時文章支援是與 `"adobeanalytics_nativeConfig"` 方法類似的解決方案。此方法的 `stats.html` 頁面可同時滿足您對 AMP 和 FIA 的分析需求。如需在 FIA 上實施追蹤的詳細資訊，請參閱 [Facebook 即時文章](fb-instant-articles.md)。
