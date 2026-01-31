---
title: 資料物件欄位對應到Adobe Analytics
description: 查看哪些資料物件欄位會被 Experience Platform Edge 自動對應至 Analytics 變數。
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: b3546e67cccc37cbdb89db2e80b3b34b2dbe417b
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 77%

---

# 資料物件欄位對應到Adobe Analytics

下表顯示Adobe Experience Platform Edge Network自動對應至Adobe Analytics的資料物件欄位。 如果您使用這些資料物件欄位路徑，則不需要額外設定即可將資料傳送至 Adobe Analytics。

如果您未來打算使用 Customer Journey Analytics，建議使用這些欄位。此實施方法允許您的組織使用 Web SDK 將資料傳送至 Adobe，而無需符合 XDM 架構。當您的組織準備將資料傳送至 Adobe Experience Platform 時，您可以使用[資料流對應](https://experienceleague.adobe.com/tw/en/docs/experience-platform/datastreams/data-prep#mapping)將資料物件欄位對應到其各自的 XDM 欄位。

## 值優先順序

此資料表中大部分的資料物件欄位都對應至[對應的XDM欄位](xdm-var-mapping.md)。 在Adobe Analytics擷取期間，值會先從XDM對應至Analytics變數。 可辨識的資料物件欄位會接著進行對應，並在對應至相同Analytics變數時覆寫先前設定的任何值。 例如，如果`data.__adobe.analytics.events`存在，則會取代原本衍生自XDM的整個事件集；事件不會跨兩個來源合併。 資料物件欄位中的空白字串(`""`)會遮蔽其點選對應的Analytics變數，即使對應的XDM欄位包含值亦然。

某些資料物件欄位亦支援其對應的[查詢參數值](../validate/query-parameters.md)作為簡寫值。只要對應到的變數是唯一的，您可以互換使用標準資料物件欄位與簡寫資料物件欄位。請避免同時設定標準資料物件欄位及其對應的簡寫資料物件欄位。Adobe 無法保證哪一個欄位會具有優先順序。

## 資料物件欄位對應

此表格先前的更新內容可在本頁面的 [GitHub 提交歷史記錄](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md)中找到。與 AppMeasurement 變數相同，所有資料物件欄位皆區分大小寫。

| 資料物件欄位路徑 | Analytics 變數與說明 |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | [瀏覽器高度](../../components/dimensions/browser-height.md)維度。也支援簡寫欄位 `data.__adobe.analytics.bh`。 |
| `data.__adobe.analytics.browserWidth` | [瀏覽器寬度](../../components/dimensions/browser-width.md)維度。也支援簡寫欄位 `data.__adobe.analytics.bw`。 |
| `data.__adobe.analytics.campaign` | [追蹤程式碼](../../components/dimensions/tracking-code.md)維度。也支援簡寫欄位 `data.__adobe.analytics.v0`。 |
| `data.__adobe.analytics.channel` | [網站區段](../../components/dimensions/site-section.md)維度。也支援簡寫欄位 `data.__adobe.analytics.ch`。 |
| `data.__adobe.analytics.colorDepth` | [色彩深度](../../components/dimensions/color-depth.md)維度。也支援簡寫欄位 `data.__adobe.analytics.c`。 |
| `data.__adobe.analytics.connectionType` | [連線類型](../../components/dimensions/connection-type.md)維度。也支援簡寫欄位 `data.__adobe.analytics.ct`。 |
| `data.__adobe.analytics.contextData` | [內容資料變數](/help/implement/vars/page-vars/contextdata.md)。 |
| `data.__adobe.analytics.cookiesEnabled` | [Cookie 支援](../../components/dimensions/cookie-support.md)維度。也支援簡寫欄位 `data.__adobe.analytics.k`。 |
| `data.__adobe.analytics.currencyCode` | [`currencyCode`](../vars/config-vars/currencycode.md) 實施變數。也支援簡寫欄位 `data.__adobe.analytics.cc`。 |
| `data.__adobe.analytics.dynamicVariablePrefix` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) 實施變數。 |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) 維度。也支援簡寫欄位 `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250`。 |
| `data.__adobe.analytics.events` | [自訂事件](../../components/metrics/custom-events.md)。請使用與 [`events`](../vars/page-vars/events/events-overview.md) 實施變數相同的格式來設定此欄位。 |
| `data.__adobe.analytics.javaEnabled` | [Java 已啟用](../../components/dimensions/java-enabled.md)維度。也支援簡寫欄位 `data.__adobe.analytics.v`。 |
| `data.__adobe.analytics.latitude` | 協助設定[位置](../../components/dimensions/lifecycle-dimensions.md)行動生命週期維度。也支援簡寫欄位 `data.__adobe.analytics.lat`。 |
| `data.__adobe.analytics.linkName` | 依據 `data.__adobe.analytics.linkType` 中的值，為[自訂連結](../../components/dimensions/custom-link.md)、[下載連結](../../components/dimensions/download-link.md)或[退出連結](../../components/dimensions/exit-link.md)維度。也支援簡寫欄位 `data.__adobe.analytics.pev2`。 |
| `data.__adobe.analytics.linkURL` | [`linkURL`](../vars/config-vars/linkurl.md) 實施變數。也支援簡寫欄位 `data.__adobe.analytics.pev1`。 |
| `data.__adobe.analytics.linkType` | 判斷所點按連結的類型。有效值包括 `o` (自訂連結)、`d` (下載連結) 和 `e` (退出連結)。也支援簡寫欄位 `data.__adobe.analytics.pe`。 |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) 實施變數。也支援簡寫欄位 `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3`。 |
| `data.__adobe.analytics.longitude` | 協助設定[位置](../../components/dimensions/lifecycle-dimensions.md)行動生命週期維度。也支援簡寫欄位 `data.__adobe.analytics.lon`。 |
| `data.__adobe.analytics.pageName` | [頁面](/help/components/dimensions/page.md)維度。 |
| `data.__adobe.analytics.pageURL` | [頁面 URL](/help/components/dimensions/page-url.md) 維度。也支援簡寫欄位 `data.__adobe.analytics.g`。 |
| `data.__adobe.analytics.pageType` | [`pageType`](../vars/page-vars/pagetype.md) 實施變數。 |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) 維度。也支援簡寫欄位 `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75`。 |
| `data.__adobe.analytics.purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) 實施變數。 |
| `data.__adobe.analytics.products` | 遵循類似的格式，這是 [`products`](../vars/page-vars/products.md) 實施變數。 |
| `data.__adobe.analytics.referrer` | [反向連結](/help/components/dimensions/referrer.md)維度。 |
| `data.__adobe.analytics.resolution` | [螢幕解析度](../../components/dimensions/monitor-resolution.md)維度。也支援簡寫欄位 `data.__adobe.analytics.s`。 |
| `data.__adobe.analytics.server` | [伺服器](/help/components/dimensions/server.md)維度。 |
| `data.__adobe.analytics.transactionID` | [`transactionID`](../vars/page-vars/transactionid.md) 實施變數。也支援簡寫欄位 `data.__adobe.analytics.xact`。 |
| `data.__adobe.analytics.zip` | [郵遞區號](../../components/dimensions/zip-code.md)維度。 |

{style="table-layout:auto"}
