---
title: XDM物件變數對應至Adobe Analytics
description: 檢視 Edge 會將哪些 XDM 欄位自動對應到 Analytics 變數。
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 5e97c9a4a3c7368cefb3cc6a7bc89a450e6e3f4a
workflow-type: tm+mt
source-wordcount: '1414'
ht-degree: 56%

---

# XDM物件變數對應至Adobe Analytics

下表顯示Adobe Experience PlatformEdge Network自動對應至Adobe Analytics的XDM變數。 如果您使用這些XDM欄位路徑，則傳送資料給Adobe Analytics不需要額外的設定。 這些欄位包含在&#x200B;**[!UICONTROL Adobe Analytics ExperienceEvent範本]**&#x200B;欄位群組中。 如果您想要將資料傳送至Adobe Analytics和Adobe Experience Platform，建議您使用這些欄位。

如果您的組織計畫移至Customer Journey Analytics，Adobe建議改用`data`物件，在不符合結構描述的情況下，直接將資料傳送至Adobe Analytics。 此策略可讓您的組織使用自己的結構描述，而不使用[!UICONTROL Adobe Analytics ExperienceEvent範本] (不太適用於Customer Journey Analytics)。 如需類似的對應表格，請參閱[對應至Adobe Analytics](data-var-mapping.md)的資料物件變數。

## 值優先順序

此資料表中的大部分XDM物件欄位都與[資料物件欄位](data-var-mapping.md)一致。 如果您同時設定指定的XDM物件欄位及其各自的資料物件欄位，資料物件欄位將會優先。 如果您同時使用XDM物件欄位和資料物件欄位，Adobe建議使用資料物件欄位設定自訂事件。 如果欄位`data.__adobe.analytics.events`存在，則會覆寫所有與商務和自訂事件相關的XDM物件欄位。

## xdm物件欄位對應

您可在本頁之 [GitHub 上的認可歷史記錄](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/xdm-var-mapping.md)上找到之前對此表格的更新。

| XDM 欄位路徑 | Analytics變數和說明 |
| --- | --- |
| `xdm.application.isClose` | 協助定義行動生命週期量度[損毀](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)。 |
| `xdm.application.isInstall` | 協助判斷何時增加行動生命週期量度[首次啟動](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)。 |
| `xdm.application.closeType` | 判斷某個關閉事件是否損毀。有效值包括 `close` (生命週期工作階段結束，並收到上一個工作階段的暫停事件) 和 `unknown` (生命週期工作階段結束且沒有暫停事件)。幫助設定行動生命週期量度[損毀](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) 指標。 |
| `xdm.application.isInstall` | 行動生命週期量度[安裝](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)。 |
| `xdm.application.isLaunch` | 行動生命週期量度[啟動](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)。 |
| `xdm.application.name` | 協助設定行動生命週期維度[應用程式 ID](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)。 |
| `xdm.application.isUpgrade` | 行動生命週期量度[升級](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)。 |
| `xdm.application.version` | 協助設定行動生命週期維度[應用程式 ID](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)。 |
| `xdm.application.sessionLength` | 行動生命週期量度[前一個工作階段長度](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)。 |
| `xdm.commerce.checkouts.id` | 將[事件序列化](../vars/page-vars/events/event-serialization.md)套用到[結帳](../../components/metrics/checkouts.md)量度。 |
| `xdm.commerce.checkouts.value` | 讓[結帳](../../components/metrics/checkouts.md)量度遞增所需的金額。 |
| `xdm.commerce.order.currencyCode` | 設定 [currencyCode](../vars/config-vars/currencycode.md) 設定變數。 |
| `xdm.commerce.order.purchaseID` | 設定 [purchaseID](../vars/page-vars/purchaseid.md) 頁面變數。 |
| `xdm.commerce.order.payments[0].transactionID` | 設定 [transactionID](../vars/page-vars/transactionid.md) 頁面變數。 |
| `xdm.commerce.productListAdds.id` | 將[事件序列化](../vars/page-vars/events/event-serialization.md)套用到[購物車新增](../../components/metrics/cart-additions.md)量度。 |
| `xdm.commerce.productListAdds.value` | 增加[購物車新增](../../components/metrics/cart-additions.md)量度。 |
| `xdm.commerce.productListOpens.id` | 將[事件序列化](../vars/page-vars/events/event-serialization.md)套用到[購物車](../../components/metrics/carts.md)量度。 |
| `xdm.commerce.productListOpens.value` | 增加[購物車](../../components/metrics/carts.md)量度。 |
| `xdm.commerce.productListRemovals.id` | 將[事件序列化](../vars/page-vars/events/event-serialization.md)套用到[購物車移除](../../components/metrics/cart-removals.md)量度。 |
| `xdm.commerce.productListRemovals.value` | 增加[購物車移除](../../components/metrics/cart-removals.md)量度。 |
| `xdm.commerce.productListViews.id` | 將[事件序列化](../vars/page-vars/events/event-serialization.md)套用到[購物車檢視](../../components/metrics/cart-views.md)量度。 |
| `xdm.commerce.productListViews.value` | 增加[購物車檢視](../../components/metrics/cart-views.md)量度。 |
| `xdm.commerce.productViews.id` | 將[事件序列化](../vars/page-vars/events/event-serialization.md)套用到[產品檢視](../../components/metrics/product-views.md)量度。 |
| `xdm.commerce.productViews.value` | 增加[產品檢視](../../components/metrics/product-views.md)量度。 |
| `xdm.commerce.purchases.value` | 增加[訂單](../../components/metrics/orders.md)量度。 |
| `xdm.device.model` | 行動生命週期維度[裝置名稱](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)。 |
| `xdm.device.colorDepth` | 協助設定[色彩深度](../../components/dimensions/color-depth.md)維度。 |
| `xdm.device.screenHeight` | 協助設定[顯示器解析度](../../components/dimensions/monitor-resolution.md)維度。 |
| `xdm.device.screenWidth` | 協助設定[顯示器解析度](../../components/dimensions/monitor-resolution.md)維度。 |
| `xdm.device.type` | 行動裝置類型。 |
| `xdm.environment.browserDetails.acceptLanguage` | 協助設定[語言](../../components/dimensions/language.md)維度。 |
| `xdm.environment.browserDetails.cookiesEnabled` | 設定 [Cookie 支援](../../components/dimensions/cookie-support.md)維度。有效值包括 `Y` (瀏覽器接受 Cookie) 和 `N` (瀏覽器拒絕 Cookie)。 |
| `xdm.environment.browserDetails.javaEnabled` | 設定 [Java 已啟用](../../components/dimensions/java-enabled.md)維度。有效值包括 `Y` (Java 已啟用) 和 `N` (Java 已停用)。 |
| `xdm.environment.browserDetails.userAgent` | 用作遞補[不重複訪客](../../components/metrics/unique-visitors.md)識別方法。通常會使用 `User-Agent` HTTP 請求標頭填入。如果您想要在報告中使用這個欄位，可以將它對應到 eVar。 |
| `xdm.environment.browserDetails.viewportHeight` | 設定[瀏覽器高度](../../components/dimensions/browser-height.md)維度。 |
| `xdm.environment.browserDetails.viewportWidth` | 設定[瀏覽器寬度](../../components/dimensions/browser-width.md)維度。 |
| `xdm.environment.carrier` | 行動生命週期維度[電信業者名稱](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)。 |
| `xdm.environment.connectionType` | 協助設定[連線類型](../../components/dimensions/connection-type.md)維度。 |
| `xdm.environment.ipV4` | 用作遞補[不重複訪客](../../components/metrics/unique-visitors.md)識別方法。通常會使用 `X-Forwarded-For` HTTP 標頭填入。 |
| `xdm.environment.language` | 行動維度地區設定。 |
| `xdm.environment.operatingSystem` | 行動生命週期維度[作業系統](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)。 |
| `xdm.environment.operatingSystemVersion` | 協助設定行動生命週期維度[作業系統版本](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/)。 |
| `xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar250` | 設定個別 [eVar](../../components/dimensions/evar.md) 維度。 |
| `xdm._experience.analytics.customDimensions.`<br/>`hierarchies.hier1`<br/>`[...]`<br/>`xdm._experience.analytics.customDImensions.`<br/>`hierarchies.hier5` | 設定個別[階層](/help/components/dimensions/hierarchy.md)維度。 |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | 清單屬性分隔符號覆寫。不建議使用此欄位，因為分隔符號是根據報告套裝設定，從[流量變數管理員](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)自動擷取。使用此欄位可能會造成所使用的分隔符號與 Analytics 預期使用的分隔符號不相符。 |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.values`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | 字串陣列含有個別[清單流量變數](../vars/page-vars/prop.md#list-props)值。 |
| `xdm._experience.analytics.customDimensions.`<br/>`lists.list1.list[].value`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | 將個別 `list[]` 陣列中的所有 `value` 字串都串連到其個別[清單變數](../vars/page-vars/list.md)。分隔符號是根據[報告套裝設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)中設置的值來自動選擇。 |
| `xdm._experience.analytics.customDimensions.`<br/>`props.prop1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`props.prop75` | 設定個別[流量變數](../../components/dimensions/prop.md)維度。 |
| `xdm._experience.analytics.event1to100.`<br/>`event1.id`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.id` | 套用[事件序列化](../vars/page-vars/events/event-serialization.md)至個別[自訂事件](../../components/metrics/custom-events.md)量度。每個事件 ID 位於其 100 群組父系中。例如，若要將序列化應用於 `event678`，請使用 `xdm._experience.analytics.event601to700.event678.id`。 |
| `xdm._experience.analytics.event1to100.`<br/>`event1.value`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.value` | 將個別[自訂事件](../../components/metrics/custom-events.md)量度增加所需的數量。每個事件位於其 100 群組父系中。例如，`event567` 的欄位是 `xdm._experience.analytics.event501to600.event567.value`。 |
| `xdm.identityMap.ECID[0].id` | [Adobe Experience Cloud 身分識別服務 ID](https://experienceleague.adobe.com/docs/id-service/using/home.html)。 |
| `xdm.marketing.trackingCode` | 設定[追蹤程式碼](../../components/dimensions/tracking-code.md)維度。 |
| `xdm.media.mediaTimed.completes.value` | 串流媒體量度[內容完成](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-complete)。 |
| `xdm.media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`、`c.a.media.timePlayed`、`c.a.media.play` |
| `xdm.media.mediaTimed.federated.value` | 串流媒體量度[同盟資料](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#federated-data)。 |
| `xdm.media.mediaTimed.firstQuartiles.value` | 串流媒體量度[25%進度標籤](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#twenty-five-progress-marker)。 |
| `xdm.media.mediaTimed.mediaSegmentView.value` | 串流媒體量度[內容區段檢視](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment-views)。 |
| `xdm.media.mediaTimed.midpoints.value` | 串流媒體量度[50%進度標籤](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#fifty-progress-marker)。 |
| `xdm.media.mediaTimed.pauseTime.value` | 串流媒體量度[總暫停期間](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#total-pause-duration)。 |
| `xdm.media.mediaTimed.pauses.value` | 串流媒體量度[暫停事件](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#pause-events)。 |
| `xdm.mediaCollection.sessionDetails.assetID` | 串流媒體維度[資產識別碼](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#asset-id)。 |
| `xdm.mediaCollection.sessionDetails.friendlyName` | 串流媒體維度[視訊名稱](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-name)。 |
| `xdm.mediaCollection.sessionDetails.originator` | 串流媒體維度[創作者](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#originator)。 |
| `xdm.mediaCollection.sessionDetails.episode` | 串流媒體維度[Episode](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#episode)。 |
| `xdm.mediaCollection.sessionDetails.genre` | 串流媒體維度[型別](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#genre)。 |
| `xdm.mediaCollection.sessionDetails.rating` | 串流媒體維度[內容評等](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-rating)。 |
| `xdm.mediaCollection.sessionDetails.season` | 串流媒體維度[季](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#season)。 |
| `xdm.mediaCollection.sessionDetails.name` | 串流媒體維度[內容識別碼](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-id)。 |
| `xdm.mediaCollection.sessionDetails.show` | 串流媒體維度[節目](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show)。 |
| `xdm.mediaCollection.sessionDetails.showType` | 串流媒體維度[節目型別](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show-type)。 |
| `xdm.mediaCollection.sessionDetails.length` | 串流媒體維度[視訊長度](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-length)。 |
| `xdm.media.mediaTimed.primaryAssetViewDetails.@id` | 串流媒體維度[媒體工作階段識別碼](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-session-id)。 |
| `xdm.mediaCollection.sessionDetails.channel` | 串流媒體維度[內容頻道](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-channel)。 |
| `xdm.mediaCollection.sessionDetails.contentType` | 串流媒體維度[內容型別](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-type)。 |
| `xdm.mediaCollection.sessionDetails.network` | 串流媒體維度[網路](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#network)。 |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | 串流媒體維度[內容區段](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment)。 |
| `xdm.mediaCollection.sessionDetails.playerName` | 串流媒體維度[內容播放器名稱](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-player-name)。 |
| `xdm.mediaCollection.sessionDetails.appVersion` | 串流媒體維度[SDK版本](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#sdk-version)。 |
| `xdm.mediaCollection.sessionDetails.feed` | 串流媒體維度[媒體摘要型別](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-feed-type)。 |
| `xdm.mediaCollection.sessionDetails.streamFormat` | 串流媒體維度[串流格式](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#stream-format)。 |
| `xdm.media.mediaTimed.progress10.value` | 串流媒體量度[1%進度標籤](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ten-progress-marker)。 |
| `xdm.media.mediaTimed.progress95.value` | 串流媒體量度[95%進度標籤](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ninety-five-progress-marker)。 |
| `xdm.mediaCollection.sessionDetails.hasResume` | 串流媒體量度[內容繼續](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-resumes)。 |
| `xdm.media.mediaTimed.starts.value` | 串流媒體量度[媒體開始](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-starts)。 |
| `xdm.media.mediaTimed.thirdQuartiles.value` | 串流媒體量度[75%進度標籤](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#seventy-five-progress-marker)。 |
| `xdm.media.mediaTimed.timePlayed.value` | 串流媒體量度[內容逗留時間](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-time-spent)。 |
| `xdm.media.mediaTimed.totalTimePlayed.value` | 串流媒體量度[媒體逗留時間](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-time-spent)。 |
| `xdm.placeContext.geo._schema.latitude` | 訪客的緯度位置。 協助設定[行動生命週期位置](/help/components/dimensions/lifecycle-dimensions.md)維度。 |
| `xdm.placeContext.geo._schema.longitude` | 訪客的經度位置。 協助設定[行動生命週期位置](/help/components/dimensions/lifecycle-dimensions.md)維度。 |
| `xdm.placeContext.geo.postalCode` | [郵遞區號](../../components/dimensions/zip-code.md)維度。 |
| `xdm.placeContext.geo.stateProvince` | [美國州別](../../components/dimensions/us-states.md)維度。 |
| `xdm.placeContext.localTime` | 在[資料摘要](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)中顯示為 `t_time_info`。 |
| `xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | 將[產品語法](../vars/page-vars/products.md)銷售套用至 eVars。 |
| `xdm.productListItems[]._experience.analytics.`<br/>`event1to100.event1.value`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | 將[產品語法](../vars/page-vars/products.md)銷售套用至事件。 |
| `xdm.productListItems[].productCategories[].categoryID` | [類別](../../components/dimensions/category.md)維度。另外請查看[產品](../vars/page-vars/products.md)頁面變數。 |
| `xdm.productListItems[].name` | [產品](../../components/dimensions/product.md)維度。另外請查看 [產品](../vars/page-vars/products.md) 頁面變數。如果 `xdm.productListItems[].SKU` 和 `xdm.productListItems[].name` 都包含資料，則使用 `xdm.productListItems[].SKU` 中的值。 |
| `xdm.productListItems[].priceTotal` | 協助判斷[收入](../../components/metrics/revenue.md)量度。另外請查看[產品](../vars/page-vars/products.md)頁面變數。 |
| `xdm.productListItems[].quantity` | 協助判斷[單位](../../components/metrics/units.md)量度。另外請查看[產品](../vars/page-vars/products.md)頁面變數。 |
| `xdm.productListItems[].SKU` | [產品](../../components/dimensions/product.md)維度。另外請查看 [產品](../vars/page-vars/products.md) 頁面變數。如果 `xdm.productListItems[].SKU` 和 `xdm.productListItems[].name` 都包含資料，則使用 `xdm.productListItems[].SKU` 中的值。 |
| `xdm.web.webInteraction.URL` | [linkURL](../vars/config-vars/linkurl.md) 實作變數。 |
| `xdm.web.webInteraction.name` | [自訂連結](../../components/dimensions/custom-link.md)、[下載連結](../../components/dimensions/download-link.md)或[退出連結](../../components/dimensions/exit-link.md)維度 (視 `xdm.web.webInteraction.type` 中的值而定) |
| `xdm.web.webInteraction.type` | 判斷點擊的連結類型。有效值包括 `other` (自訂連結)、`download` (下載連結) 和 `exit` (退出連結)。 |
| `xdm.web.webPageDetails.URL` | [頁面 URL](../../components/dimensions/page-url.md) 維度。 |
| `xdm.web.webPageDetails.isErrorPage` | 有助於判斷「找不到頁面」[維度](../../components/dimensions/pages-not-found.md)和[量度](../../components/metrics/pages-not-found.md)的旗標。 |
| `xdm.web.webPageDetails.name` | [頁面](../../components/dimensions/page.md)維度。 |
| `xdm.web.webPageDetails.server` | [伺服器](../../components/dimensions/server.md)維度。 |
| `xdm.web.webPageDetails.siteSection` | [網站區段](../../components/dimensions/site-section.md)維度。 |
| `xdm.web.webReferrer.URL` | [反向連結](../../components/dimensions/referrer.md)維度。 |

{style="table-layout:auto"}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## 將其他 XDM 欄位對應到 Analytics 變數

如果有任何維度或量度要新增至Adobe Analytics，您可以透過[內容資料變數](../vars/page-vars/contextdata.md)來進行。

### 隱含對應

所有未自動對應的XDM欄位元素都會當作前置詞為`a.x.`的內容資料傳送到Adobe Analytics。您接著可以使用[處理規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html)將此內容資料變數對應到所要的Analytics變數。 例如，如果您傳送以下事件︰

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

Web SDK 會將該資料當作內容資料變數 `a.x._atag.search.term` 傳送給 Adobe Analytics。然後，您可以使用處理規則將該內容資料變數值指派給所需的Analytics變數，例如`eVar`：

![搜尋字詞處理規則](assets/examplerule.png)

## 明確對應

您也可以將XDM欄位元素明確對應為內容資料。 使用`contextData`元素明確對應的任何XDM欄位元素都會當作無首碼的內容資料傳送到Adobe Analytics。 您可以使用[處理規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html)將此內容資料變數對應到所需的 Analytics 變數。 例如，如果您傳送以下事件︰

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "analytics": {
                "contextData" : {
                    "someValue" : "1"
                }
            }
        }
    }
})
```

Web SDK會將該資料以內容資料變數`somevalue`的形式傳送至Adobe Analytics，其值為`1`。  然後，您可以使用處理規則將該內容資料變數值指派給所需的Analytics變數，例如`eVar`：

![搜尋字詞處理規則](assets/examplerule-explicit.png)
