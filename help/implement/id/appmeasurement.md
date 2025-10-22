---
title: 使用AppMeasurement識別訪客
description: 使用AppMeasurement實作Adobe Analytics時正確識別訪客。
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# 使用AppMeasurement識別訪客

AppMeasurement是Adobe Analytics的舊版JavaScript資料庫，用於資料收集。 雖然AppMeasurement本身提供可識別訪客的原生方式，但許多現代瀏覽器會拒絕嘗試設定的第三方Cookie。 Adobe強烈建議在所有實作中使用Adobe Experience Cloud訪客ID服務，以遵循現代化的瀏覽器隱私權標準。 所有版本的AppMeasurement都隨附`VisitorAPI.js`，這是用來實作訪客ID服務的JavaScript資料庫。

## 使用訪客ID服務識別訪客（建議）

請確定您已做好下列準備：

* 下載[最新版本的AppMeasurement](https://github.com/adobe/appmeasurement)。 下載的程式庫包含`AppMeasurement.js`和`VisitorAPI.js`。
* 開發[報表套裝ID](/help/admin/tools/manage-rs/new-rs/new-report-suite.md)。
* [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md)的所需邊緣網域。
* 您的IMS組織ID：
   1. 使用您的Adobe ID憑證登入[experience.adobe.com](https://experience.adobe.com)。
   1. 在Experience Cloud介面中的任何位置，按下`[Cmd]` + `[I]` (iOS)或`[Ctrl]` + `[I]` (Windows)。
   1. 出現&#x200B;**[!UICONTROL 使用者資料偵錯工具]**。 選取&#x200B;**[!UICONTROL 指派的組織]**&#x200B;索引標籤。
   1. 展開所需的IMS組織。
   1. 找到&#x200B;**[!UICONTROL ID]**&#x200B;欄位。

擁有上述資源後，下列基本範例頁面會包含將資料傳送至Adobe Analytics所需的最低呼叫：

```html
<html>
  <head>
    <title>Example AppMeasurement implementation page</title>
    <script src="AppMeasurement.js"></script>
    <script src="VisitorAPI.js"></script>
  </head>
  <body>
    <h1>Hello world!</h1>
    <script>
      var s = s_gi("examplersid"); // Include development report suite ID here
      s.trackingServerSecure = "example.data.adobedc.net"; // Include edge domain here
      s.visitor = Visitor.getInstance("ADB3LETTERSANDNUMBERS@AdobeOrg"); // Include IMS org ID here
      s.pageName = document.title;
      s.t();
    </script>
  </body>
</html>
```

>[!TIP]
>
>您可以透過將`Visitor`的存在指派給[`doPlugins`](/help/implement/vars/functions/doplugins.md)中的自訂變數來追蹤點選是否使用訪客ID服務：
>
>```js
>s.doPlugins = function() {
>   s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI present" : "VisitorAPI missing";
>};
>```

## 使用`s_vi` Cookie識別訪客（不建議）

>[!IMPORTANT]
>
>Adobe建議不要使用此方法來識別訪客。

如果貴組織未使用訪客ID服務，AppMeasurement會使用專屬的訪客身分識別形式。 當訪客首次進入您的網站時，資料庫會檢查[`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookie。 此Cookie設定於符合[`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) （適用於HTTPS）或[`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) （適用於HTTP）的網域中。

* 如果您參與[Managed憑證方案](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert)，您的追蹤伺服器通常會是第一方網域，使`s_vi` Cookie成為第一方。
* 如果您不參與Managed憑證方案，追蹤伺服器通常是`adobedc.net`、`omtrdc.net`或`2o7.net`的子網域，使`s_vi` Cookie成為協力廠商Cookie。 由於現今瀏覽器隱私權標準限制，大部分的瀏覽器都會拒絕第三方Cookie。 在遭到拒絕後，AppMeasurement會嘗試改為設定第一方備援Cookie (`fid`)。

如果您正確設定`trackingServerSecure`，則不需要進一步的訪客識別測量。

## 使用`visitorID`識別訪客（不建議）

>[!IMPORTANT]
>
>Adobe建議不要使用此方法來識別訪客。

使用[`visitorID`](/help/implement/vars/config-vars/visitorid.md)變數可讓您的組織完成識別訪客的獨立控制。 如果您使用`visitorID`，請注意下列限制：

* 每個點選都必須包含相同的`visitorID`值，才能計為單一訪客。
   * 任何省略`visitorID`的點選都會自動嘗試使用其他訪客識別方法，將其視為個別訪客。
   * 任何包含與先前點選不同的`visitorID`值的點選會視為個別訪客。
   * Adobe不提供在Adobe Analytics中使用不同訪客ID來拼接點選的方法。
* 使用`visitorID`識別的訪客不支援共用受眾、Analytics for Target和Customer屬性。

如需使用此變數的實作指示，請參閱[`visitorID`](/help/implement/vars/config-vars/visitorid.md)。
