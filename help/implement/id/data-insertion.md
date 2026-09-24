---
title: 使用資料插入API識別訪客
description: 透過資料插入API，識別伺服器端和直接Adobe Analytics資料收集的訪客。
feature: Implementation Basics
role: Admin, Developer, Leader
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7fcd738b7eb13c13d5f9f23d625287988c803220
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 0%
---
# 使用資料插入API識別訪客

[資料插入API](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)將點選傳送至Adobe Analytics收集伺服器，而不需要使用者端資料庫，例如AppMeasurement或Web SDK。 由於沒有資料庫可為您管理身分識別，因此您需自行設定訪客識別碼（在瀏覽器中針對直接影像請求設定，或在您的伺服器上針對伺服器端集合設定）。

>[!NOTE]
>
>本頁說明訪客身分識別。 若要建置和傳送要求本身，請參閱Adobe Developer上的[資料插入API檔案](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)。

Adobe使用標準[操作順序](overview.md)來識別訪客： `vid`，然後是`aid`、`mid`、`fid`，最後是IP位址和使用者代理程式。 透過資料插入API，您通常會直接設定三個識別碼之一：ECID (`mid`)、Analytics訪客識別碼(`aid`)或自訂訪客識別碼(`vid`)。

## 使用ECID （建議）

ECID （以`mid`形式傳送）是現代版的跨解決方案訪客識別碼，可跨Adobe Analytics、Adobe Target和Adobe Audience Manager共用。 Adobe建議儘可能使用。

取得[訪客ID服務](https://experienceleague.adobe.com/tw/en/docs/id-service/using/home) (`VisitorAPI.js`)的ECID。 在瀏覽器中，使用[`getInstance`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getinstance)以您的IMS組織ID初始化服務，然後使用[`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid)讀取ECID：

```js
var visitor = Visitor.getInstance("YOUR_ORG_ID@AdobeOrg");
var ecid = visitor.getMarketingCloudVisitorID();
```

在每次點選時將該值當作`mid`查詢引數傳送，並將您的IMS組織ID當作`mcorgid`引數傳送，以便ECID正確解析。 如果您的資料轉送到Audience Manager，請同時從[`getLocationHint`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getlocationhint)傳送地區作為`aamlh`引數。 若要將您自己的客戶識別碼與訪客建立關聯，請使用[`setCustomerIDs`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/setcustomerids)。

如需伺服器端收集，請取得使用者端上的ECID，並將其轉寄至您的伺服器，以便在每次點選時傳送。 若要在沒有使用者端的情況下完全在伺服器端產生ECID，請使用ID服務的[直接整合](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/direct-integration)。

## 使用Analytics訪客識別碼

Analytics訪客識別碼(`aid`)儲存在[`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookie中。 當點選到達時沒有識別碼，收集伺服器會指派`aid`並嘗試設定包含該識別碼的Cookie。 有些[回應型別](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types)也在回應本文中包含此識別碼。

* **使用者端（直接影像要求）。** 瀏覽器會儲存伺服器傳回的`s_vi` Cookie，並在後續每次要求時將它傳送至相同的集合網域。 接著會自動辨識該訪客，且不需要自行設定`aid`。 由於此模型依賴Cookie，因此具有和任何Cookie型身分相同的耐用性限制。 請參閱使用AppMeasurement的[訪客身分識別](appmeasurement.md)以瞭解第一方與第三方Cookie行為，以及[作業順序](overview.md)，瞭解Adobe如何選擇要使用的識別碼。 Adobe建議使用ECID來建立永續性身分。

  >[!NOTE]
  >
  >如果您直接從`s_vi` Cookie讀取訪客ID，Cookie會以其他資料（例如`[CS]v1|<id>[CE]`）包裝ID — 僅擷取`<id>`部分。 從訪客回應中讀取ID時，會直接傳回該ID，而不會進行剖析。

* **伺服器端。** 伺服器沒有Cookie Jar，因此您自行儲存並重新傳送`aid`，並輸入給使用者：

  1. 查詢使用者已儲存的`aid`。
  1. 如果您有查詢引數，請以`aid`查詢引數的形式傳送。
  1. 若未包含，請傳送不含識別碼的點選，要求傳回指派的`aid`的回應型別，然後儲存以供下次使用。

  第一個無識別碼點選已歸因於伺服器傳回的`aid`，因此您在取得ID之前就先傳送資料，不會遺失任何資料。 對於傳回識別碼（`3`用於JavaScript，`11`用於XML，`10`用於JSON）和要求格式的回應型別，請參閱資料插入API檔案中的[回應型別](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types)。

  伺服器端要求不攜帶訪客Cookie，而且其專屬的IP位址和使用者代理程式屬於傳送者。 若要正確歸因點選，同時轉送訪客的實際IP位址（`X-Forwarded-For`標頭）和使用者代理程式（`User-Agent`標頭）。

## 使用自訂訪客ID

如果您已有可完全控制的永續性識別碼，則可在每次點選時以[`visitorID`](/help/implement/vars/config-vars/visitorid.md) (`vid`)的身分傳送，且您可擁有端對端的識別碼。 這適用於提供穩定裝置識別碼的非瀏覽器平台。 例如，Unity應用程式可以傳送其裝置識別碼做為`vid`。

>[!IMPORTANT]
>
>只有在您可以保證每次點選都有穩定值時，才使用`vid`：
>
>* **瀏覽器不適合使用。** 瀏覽器沒有您可以可靠填入的永續性識別碼，因此瀏覽器組別`vid`容易出現片段或衝突。 請改用Cookie型使用者端模式。
>* **請謹慎使用驗證識別碼。** 您無法在使用者登入前取得識別碼，且如果使用者登出，後續的點選會歸因於不同訪客。 這些動作會將一個人的活動分割成多個訪客。

如需自訂訪客ID的格式與限制，請參閱[`visitorID`](/help/implement/vars/config-vars/visitorid.md)。
