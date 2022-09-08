---
title: Adobe Experience Edge 中的 Analytics 變數對應
description: 檢視 Edge 會將哪些 XDM 欄位自動對應到 Analytics 變數。
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
source-git-commit: e42c125da0c48ff01267e3a18aaec8374652809e
workflow-type: tm+mt
source-wordcount: '1386'
ht-degree: 99%

---

# Adobe Experience Edge 中的 Analytics 變數對應

下表顯示 Adobe Experience Platform Edge Network 自動對應到 Adobe Analytics 中的變數。 如果您使用 XDM 欄位路徑，則傳送資料給 Adobe Analytics 不需要額外的設定。

| XDM 欄位路徑 | Analytics 維度和說明 |
| --- | --- |
| `application.isClose` | 協助定義行動量度[損毀](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics)。 |
| `application.isInstall` | 協助判斷何時增加行動量度[首次啟動](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics)。 |
| `application.isLaunch` | 協助判斷何時增加行動量度[首次啟動](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics)。 |
| `application.closeType` | 判斷某個關閉事件是否損毀。有效值包括 `close` (生命週期工作階段結束，並收到上一個工作階段的暫停事件) 和 `unknown` (生命週期工作階段結束且沒有暫停事件)。協助設定[損毀](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics)量度。 |
| `application.isInstall` | 行動量度[安裝](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics)。 |
| `application.isLaunch` | 行動量度[啟動](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics)。 |
| `application.name` | 協助設定行動維度[應用程式 ID](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions)。 |
| `application.isUpgrade` | 行動量度[升級](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics)。 |
| `application.version` | 協助設定行動維度[應用程式 ID](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions)。 |
| `application.sessionLength` | 行動量度[前一個工作階段長度](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics)。 |
| `commerce.checkouts.id` | 將[事件序列化](../vars/page-vars/events/event-serialization.md)套用到[結帳](../../components/metrics/checkouts.md)量度。 |
| `commerce.checkouts.value` | 讓[結帳](../../components/metrics/checkouts.md)量度遞增所需的金額。 |
| `commerce.order.currencyCode` | 設定 [currencyCode](../vars/config-vars/currencycode.md) 設定變數。 |
| `commerce.order.purchaseID` | 設定 [purchaseID](../vars/page-vars/purchaseid.md) 頁面變數。 |
| `commerce.order.transactionID` | 設定 [transactionID](../vars/page-vars/transactionid.md) 頁面變數。 |
| `commerce.productListAdds.id` | 將[事件序列化](../vars/page-vars/events/event-serialization.md)套用到[購物車新增](../../components/metrics/cart-additions.md)量度。 |
| `commerce.productListAdds.value` | 增加[購物車新增](../../components/metrics/cart-additions.md)量度。 |
| `commerce.productListOpens.id` | 將[事件序列化](../vars/page-vars/events/event-serialization.md)套用到[購物車](../../components/metrics/carts.md)量度。 |
| `commerce.productListOpens.value` | 增加[購物車](../../components/metrics/carts.md)量度。 |
| `commerce.productListRemovals.id` | 將[事件序列化](../vars/page-vars/events/event-serialization.md)套用到[購物車移除](../../components/metrics/cart-removals.md)量度。 |
| `commerce.productListRemovals.value` | 增加[購物車移除](../../components/metrics/cart-removals.md)量度。 |
| `commerce.productListViews.id` | 將[事件序列化](../vars/page-vars/events/event-serialization.md)套用到[購物車檢視](../../components/metrics/cart-views.md)量度。 |
| `commerce.productListViews.value` | 增加[購物車檢視](../../components/metrics/cart-views.md)量度。 |
| `commerce.productViews.id` | 將[事件序列化](../vars/page-vars/events/event-serialization.md)套用到[產品檢視](../../components/metrics/product-views.md)量度。 |
| `commerce.productViews.value` | 增加[產品檢視](../../components/metrics/product-views.md)量度。 |
| `commerce.purchases.value` | 增加[訂單](../../components/metrics/orders.md)量度。 |
| `device.model` | 行動維度[裝置名稱](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions)。 |
| `device.colorDepth` | 協助設定[色彩深度](../../components/dimensions/color-depth.md)維度。 |
| `device.screenHeight` | 協助設定[顯示器解析度](../../components/dimensions/monitor-resolution.md)維度。  |
| `device.screenWidth` | 協助設定[顯示器解析度](../../components/dimensions/monitor-resolution.md)維度。  |
| `device.type` | 行動裝置類型。 |
| `environment.browserDetails.acceptLanguage` | 協助設定[語言](../../components/dimensions/language.md)維度。 |
| `environment.browserDetails.cookiesEnabled` | 設定 [Cookie 支援](../../components/dimensions/cookie-support.md)維度。 有效值包括 `Y` (瀏覽器接受 Cookie) 和 `N` (瀏覽器拒絕 Cookie)。 |
| `environment.browserDetails.javaEnabled` | 設定 [Java 已啟用](../../components/dimensions/java-enabled.md)維度。 有效值包括 `Y` (Java 已啟用) 和 `N` (Java 已停用)。 |
| `environment.browserDetails.userAgent` | 用作遞補[不重複訪客](../../components/metrics/unique-visitors.md)識別方法。 通常會使用 `User-Agent` HTTP 請求標頭填入。 如果您想要在報表中使用這個欄位，可以將它對應到 eVar。 |
| `environment.browserDetails.viewportHeight` | 設定[瀏覽器高度](../../components/dimensions/browser-height.md)維度。 |
| `environment.browserDetails.viewportWidth` | 設定[瀏覽器寬度](../../components/dimensions/browser-width.md)維度。 |
| `environment.carrier` | 行動維度[電信業者名稱](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions)。 |
| `environment.connectionType` | 協助設定[連線類型](../../components/dimensions/connection-type.md)維度。 |
| `environment.ipV4` | 用作遞補[不重複訪客](../../components/metrics/unique-visitors.md)識別方法。 通常會使用 `X-Forwarded-For` HTTP 標頭填入。 |
| `environment.language` | 行動維度地區設定。 |
| `environment.operatingSystem` | 行動維度[作業系統](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions)。 |
| `environment.operatingSystemVersion` | 協助設定[作業系統版本](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions)維度。 |
| `_experience.analytics.customDimensions.`<br/>`eVars.eVar1` -<br/>`_experience.analytics.customDimensions.`<br/>`eVars.eVar250` | 設定個別 [eVar](../../components/dimensions/evar.md) 維度。 |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | 分隔符號用於提供的[清單流量變數](../vars/page-vars/prop.md#list-props)。 |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.values` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | 字串陣列含有個別[清單流量變數](../vars/page-vars/prop.md#list-props)值。 |
| `_experience.analytics.customDimensions.`<br/>`lists.list1.list[].value` -<br/>`_experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | 使用逗號分隔符號將每個各別 `list[]` 陣列中的所有 `value` 字串都串連到其各別的 [清單變數](../vars/page-vars/list.md)。 |
| `_experience.analytics.customDimensions.`<br/>`props.prop1` -<br/>`_experience.analytics.customDimensions.`<br/>`props.prop75` | 設定個別[流量變數](../../components/dimensions/prop.md)維度。 |
| `_experience.analytics.event1to100.`<br/>`event1.id` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.id` | 套用[事件序列化](../vars/page-vars/events/event-serialization.md)至個別[自訂事件](../../components/metrics/custom-events.md)量度。 |
| `_experience.analytics.event1to100.`<br/>`event1.value` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.value` | 將個別[自訂事件](../../components/metrics/custom-events.md)量度增加所需的數量。 |
| `identityMap.ECID[0].id` | [Adobe Experience Cloud 身分識別服務 ID](https://experienceleague.adobe.com/docs/id-service/using/home.html)。 |
| `marketing.trackingCode` | 設定[追蹤程式碼](../../components/dimensions/tracking-code.md)維度。 |
| `media.mediaTimed.completes.value` | Media Analytics 量度[內容完成](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-complete)。 |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`、`c.a.media.timePlayed`、`c.a.media.play` |
| `media.mediaTimed.federated.value` | Media Analytics 量度[同盟資料](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#federated-data)。 |
| `media.mediaTimed.firstQuartiles.value` | Media Analytics 量度[進度標記的 25%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#twenty-five-progress-marker)。 |
| `media.mediaTimed.mediaSegmentView.value` | Media Analytics 量度[內容區段檢視](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment-views)。 |
| `media.mediaTimed.midpoints.value` | Media Analytics 量度[進度標記的 50%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#fifty-progress-marker)。 |
| `media.mediaTimed.pauseTime.value` | Media Analytics 量度[總暫停期間](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#total-pause-duration)。 |
| `media.mediaTimed.pauses.value` | Media Analytics 量度[暫停事件](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#pause-events)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`@id` | Media Analytics 維度[資產 ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#asset-id)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | Media Analytics 維度[影片名稱](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-name)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | Media Analytics 維度[建立者](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#originator)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | Media Analytics 維度[劇集](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#episode)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | Media Analytics 維度[類別](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#genre)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | Media Analytics 維度[內容評分](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-rating)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | Media Analytics 維度[季別](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#season)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | Media Analytics 維度[內容 ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-id)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | Media Analytics 維度[顯示](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`showType` | Media Analytics 維度[顯示類型](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show-type)。 |
| `media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | Media Analytics 維度[影片長度](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-length)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | Media Analytics 維度[媒體工作階段 ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-session-id)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | Media Analytics 維度[內容頻道](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-channel)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | Media Analytics 維度[內容類型](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-type)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | Media Analytics 維度[網路](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#network)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | Media Analytics 維度[內容區段](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | Media Analytics 維度[內容播放器名稱](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-player-name)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | Media Analytics 維度 [SDK 版本](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#sdk-version)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | Media Analytics 維度[媒體摘要類型](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-feed-type)。 |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | Media Analytics 維度[串流格式](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#stream-format)。 |
| `media.mediaTimed.progress10.value` | Media Analytics 量度[進度標記的 10%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ten-progress-marker)。 |
| `media.mediaTimed.progress95.value` | Media Analytics 量度[進度標記的 95%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ninety-five-progress-marker)。 |
| `media.mediaTimed.resumes.value` | Media Analytics 量度[內容履歷](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-resumes)。 |
| `media.mediaTimed.starts.value` | Media Analytics 量度[媒體開始](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-starts)。 |
| `media.mediaTimed.thirdQuartiles.value` | Media Analytics 量度[進度標記的 75%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#seventy-five-progress-marker)。 |
| `media.mediaTimed.timePlayed.value` | Media Analytics 量度[內容花費時間](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-time-spent)。 |
| `media.mediaTimed.totalTimePlayed.value` | Media Analytics 量度[媒體花費時間](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-time-spent)。 |
| `placeContext.geo.latitude` | 行動維度 - 緯度。 |
| `placeContext.geo.longitude` | 行動維度 - 經度。 |
| `placeContext.geo.postalCode` | [郵遞區號](../../components/dimensions/zip-code.md)維度。 |
| `placeContext.geo.stateProvince` | [美國州別](../../components/dimensions/us-states.md)維度。 |
| `productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1` -<br/>`productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | 將[產品語法](../vars/page-vars/products.md)銷售套用至 eVars。 |
| `productListItems[]._experience.analytics.`<br/>`event1to100.event1.value` -<br/>`productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | 將[產品語法](../vars/page-vars/products.md)銷售套用至事件。 |
| `productListItems[].lineItemId` | [類別](../../components/dimensions/category.md)維度。另外請查看[產品](../vars/page-vars/products.md)頁面變數。 |
| `productListItems[].name` | [產品](../../components/dimensions/product.md)維度。另外請查看 [產品](../vars/page-vars/products.md) 頁面變數。如果 `productListItems[].SKU` 和 `productListItems[].name` 都包含資料，則使用 `productListItems[].SKU` 中的值。 |
| `productListItems[].priceTotal` | 協助判斷[收入](../../components/metrics/revenue.md)量度。另外請查看[產品](../vars/page-vars/products.md)頁面變數。 |
| `productListItems[].quantity` | 協助判斷[單位](../../components/metrics/units.md)量度。另外請查看[產品](../vars/page-vars/products.md)頁面變數。 |
| `productListItems[].SKU` | [產品](../../components/dimensions/product.md)維度。另外請查看 [產品](../vars/page-vars/products.md) 頁面變數。如果 `productListItems[].SKU` 和 `productListItems[].name` 都包含資料，則使用 `productListItems[].SKU` 中的值。 |
| `web.webInteraction.URL` | [linkURL](../vars/config-vars/linkurl.md) 實作變數。 |
| `web.webInteraction.name` | [自訂連結](../../components/dimensions/custom-link.md)、[下載連結](../../components/dimensions/download-link.md)或[退出連結](../../components/dimensions/exit-link.md)維度 (視 `web.webInteraction.type` 中的值而定) |
| `web.webInteraction.type` | 判斷點擊的連結類型。 有效值包括 `other` (自訂連結)、`download` (下載連結) 和 `exit` (退出連結)。 |
| `web.webPageDetails.URL` | [頁面 URL](../../components/dimensions/page-url.md) 維度。 |
| `web.webPageDetails.errorPage` | 有助於判斷「找不到頁面」[維度](../../components/dimensions/pages-not-found.md)和[量度](../../components/metrics/pages-not-found.md)的旗標。 |
| `web.webPageDetails.name` | [頁面](../../components/dimensions/page.md)維度。 |
| `web.webPageDetails.server` | [伺服器](../../components/dimensions/server.md)維度。 |
| `web.webPageDetails.siteSection` | [網站區段](../../components/dimensions/site-section.md)維度。 |
| `web.webReferrer.URL` | [反向連結](../../components/dimensions/referrer.md)維度。 |

{style=&quot;table-layout:auto&quot;}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## 將其他 XDM 欄位對應到 Analytics 變數

如果您想要將任何維度或量度新增到 Adobe Analytics，可以透過[內容資料變數](../vars/page-vars/contextdata.md)來進行。 所有不會自動對應的 XDM 欄位元素都會當作前置詞為 a.x 的內容資料傳送到 Adobe Analytics。然後您可以使用[處理規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=zh-Hant)將此內容資料變數對應到所要的 Analytics 變數。 例如，如果您傳送以下事件︰

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "search":{
                "term":"Example search term"
            }
        }
    }
})
```

Web SDK 會將該資料當作內容資料變數 `a.x._atag.search.term` 傳送給 Adobe Analytics。 然後您可以使用處理規則將該內容資料變數值指派給所需的 Analytics 變數 (例如 eVar)：

![搜尋字詞處理規則](assets/examplerule.png)
