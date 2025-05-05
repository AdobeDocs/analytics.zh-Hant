---
title: 資料物件變數對應至Adobe Analytics
description: 檢視Experience Platform Edge會自動對應到Analytics變數的資料物件欄位。
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 59d9dd8055a13046d05ac4c3b5261a6c5a919b5c
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 2%

---

# 資料物件變數對應至Adobe Analytics

下表顯示Adobe Experience PlatformEdge Network自動對應至Adobe Analytics的資料物件變數。 如果您使用這些資料物件欄位路徑，則傳送資料至Adobe Analytics不需要額外的設定。

如果您日後打算使用Customer Journey Analytics，建議使用這些欄位。 此實作方法可讓您的組織使用Web SDK傳送資料給Adobe，而不符合XDM結構描述。 當您的組織準備好將資料傳送至Adobe Experience Platform時，您可以使用[資料流對應](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/data-prep#mapping)將資料物件欄位指向其各自的XDM欄位。

## 值優先順序

此表格中的大部分資料物件欄位都與[對應的XDM欄位](xdm-var-mapping.md)一致。 如果您同時設定指定的資料物件欄位及其各自的XDM欄位，則資料物件欄位優先。 例如，如果欄位`data.__adobe.analytics.events`存在，則會覆寫所有與事件相關的XDM物件欄位。

某些資料物件欄位也支援其各自的[查詢引數值](../validate/query-parameters.md)做為速記值。 您可以互動使用標準資料物件欄位和速記資料物件欄位，只要它們分別用於唯一變數即可。 請避免同時設定標準資料物件欄位及其各自的速記資料物件欄位。 Adobe無法保證哪個欄位優先。

## 資料物件欄位對應

此資料表的先前更新可以在GitHub[&#128279;](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md)上此頁面的認可歷程記錄中找到。 與AppMeasurement變數類似，所有資料物件欄位都區分大小寫。

| 資料物件欄位路徑 | Analytics變數和說明 |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | [瀏覽器高度](../../components/dimensions/browser-height.md)維度。 也支援簡寫欄位`data.__adobe.analytics.bh`。 |
| `data.__adobe.analytics.browserWidth` | [瀏覽器寬度](../../components/dimensions/browser-width.md)維度。 也支援簡寫欄位`data.__adobe.analytics.bw`。 |
| `data.__adobe.analytics.campaign` | [追蹤代碼](../../components/dimensions/tracking-code.md)維度。 也支援簡寫欄位`data.__adobe.analytics.v0`。 |
| `data.__adobe.analytics.channel` | [網站區段](../../components/dimensions/site-section.md)維度。 也支援簡寫欄位`data.__adobe.analytics.ch`。 |
| `data.__adobe.analytics.colorDepth` | [色彩深度](../../components/dimensions/color-depth.md)維度。 也支援簡寫欄位`data.__adobe.analytics.c`。 |
| `data.__adobe.analytics.connectionType` | [連線型別](../../components/dimensions/connection-type.md)維度。 也支援簡寫欄位`data.__adobe.analytics.ct`。 |
| `data.__adobe.analytics.contextData` | [內容資料變數](/help/implement/vars/page-vars/contextdata.md)。 |
| `data.__adobe.analytics.cookiesEnabled` | [Cookie支援](../../components/dimensions/cookie-support.md)維度。 也支援簡寫欄位`data.__adobe.analytics.k`。 |
| `data.__adobe.analytics.currencyCode` | [`currencyCode`](../vars/config-vars/currencycode.md)實作變數。 也支援簡寫欄位`data.__adobe.analytics.cc`。 |
| `data.__adobe.analytics.dynamicVariablePrefix` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md)實作變數。 |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md)維度。 也支援速記欄位`data.__adobe.analytics.v1` - `data.__adobe.analytics.v250`。 |
| `data.__adobe.analytics.events` | [自訂事件](../../components/metrics/custom-events.md)。 格式化此欄位的方式與[`events`](../vars/page-vars/events/events-overview.md)實作變數類似。 |
| `data.__adobe.analytics.javaEnabled` | [Java已啟用](../../components/dimensions/java-enabled.md)維度。 也支援簡寫欄位`data.__adobe.analytics.v`。 |
| `data.__adobe.analytics.latitude` | 協助設定[位置](../../components/dimensions/lifecycle-dimensions.md)行動生命週期維度。 也支援簡寫欄位`data.__adobe.analytics.lat`。 |
| `data.__adobe.analytics.linkName` | [自訂連結](../../components/dimensions/custom-link.md)、[下載連結](../../components/dimensions/download-link.md)或[退出連結](../../components/dimensions/exit-link.md)維度（視`data.__adobe.analytics.linkType`中的值而定）。 也支援簡寫欄位`data.__adobe.analytics.pev2`。 |
| `data.__adobe.analytics.linkURL` | [`linkURL`](../vars/config-vars/linkurl.md)實作變數。 也支援簡寫欄位`data.__adobe.analytics.pev1`。 |
| `data.__adobe.analytics.linkType` | 判斷點擊的連結類型。有效值包括`o` （自訂連結）、`d` （下載連結）和`e` （退出連結）。 也支援簡寫欄位`data.__adobe.analytics.pe`。 |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md)個實作變數。 也支援速記欄位`data.__adobe.analytics.l1` - `data.__adobe.analytics.list3`。 |
| `data.__adobe.analytics.longitude` | 協助設定[位置](../../components/dimensions/lifecycle-dimensions.md)行動生命週期維度。 也支援簡寫欄位`data.__adobe.analytics.lon`。 |
| `data.__adobe.analytics.pageName` | [頁面](/help/components/dimensions/page.md)維度。 |
| `data.__adobe.analytics.pageURL` | [頁面URL](/help/components/dimensions/page-url.md)維度。 也支援簡寫欄位`data.__adobe.analytics.g`。 |
| `data.__adobe.analytics.pageType` | [`pageType`](../vars/page-vars/pagetype.md)實作變數。 |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md)維度。 也支援速記欄位`data.__adobe.analytics.c1` - `data.__adobe.analytics.c75`。 |
| `data.__adobe.analytics.purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md)實作變數。 |
| `data.__adobe.analytics.products` | [`products`](../vars/page-vars/products.md)實作變數，格式類似。 |
| `data.__adobe.analytics.referrer` | [反向連結](/help/components/dimensions/referrer.md)維度。 |
| `data.__adobe.analytics.resolution` | [監視器解析度](../../components/dimensions/monitor-resolution.md)維度。 也支援簡寫欄位`data.__adobe.analytics.s`。 |
| `data.__adobe.analytics.server` | [伺服器](/help/components/dimensions/server.md)維度。 |
| `data.__adobe.analytics.transactionID` | [`transactionID`](../vars/page-vars/transactionid.md)實作變數。 也支援簡寫欄位`data.__adobe.analytics.xact`。 |
| `data.__adobe.analytics.zip` | [郵遞區號](../../components/dimensions/zip-code.md)維度。 |

{style="table-layout:auto"}
