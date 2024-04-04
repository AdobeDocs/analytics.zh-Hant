---
title: 資料物件變數對應至Adobe Analytics
description: 檢視Experience Platform Edge會將哪些資料物件欄位自動對應至Analytics變數。
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 3a530e3e47ac9d6cf2b711cecd07f2c33765d63c
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 5%

---

# 資料物件變數對應至Adobe Analytics

下表顯示Adobe Experience Platform Edge Network自動對應至Adobe Analytics的資料物件變數。 如果您使用這些資料物件欄位路徑，則傳送資料至Adobe Analytics不需要額外的設定。

如果您日後打算使用Customer Journey Analytics，建議使用這些欄位。 此實作方法可讓您的組織使用Web SDK傳送資料給Adobe，而不符合XDM結構描述。 當貴組織準備好將資料傳送至Adobe Experience Platform時，您可使用 [資料流對應](https://experienceleague.adobe.com/docs/experience-platform/datastreams/data-prep.html#mapping) 將資料物件欄位指向各自的XDM欄位。

## 值優先順序

此表格中的大部分資料物件欄位都與 [對應的XDM欄位](xdm-var-mapping.md). 如果您同時設定兩個 `data` 物件欄位和其個別XDM欄位，資料物件欄位優先。 如果您同時使用XDM物件欄位和資料物件欄位，Adobe建議使用資料物件欄位設定自訂事件。 如果欄位 `data.__adobe.analytics.events` 出現，則會覆寫與商務和自訂事件相關的所有XDM物件欄位。

有些資料物件欄位也支援各自的欄位 [查詢引數值](../validate/query-parameters.md) 做為速記值。 您可以互動使用標準資料物件欄位和速記資料物件欄位，只要它們分別用於唯一變數即可。 請避免同時設定標準資料物件欄位及其各自的速記資料物件欄位。 Adobe無法保證哪個欄位優先。

## 資料物件欄位對應

您可在本頁之 [GitHub 上的認可歷史記錄](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md)上找到之前對此表格的更新。

| 資料物件欄位路徑 | Analytics變數和說明 |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | 此 [瀏覽器高度](../../components/dimensions/browser-height.md) 維度。 速記欄位 `data.__adobe.analytics.bh` 也受支援。 |
| `data.__adobe.analytics.browserWidth` | 此 [瀏覽器寬度](../../components/dimensions/browser-width.md) 維度。 速記欄位 `data.__adobe.analytics.bw` 也受支援。 |
| `data.__adobe.analytics.campaign` | 此 [追蹤程式碼](../../components/dimensions/tracking-code.md) 維度。 速記欄位 `data.__adobe.analytics.v0` 也受支援。 |
| `data.__adobe.analytics.channel` | 此 [網站區段](../../components/dimensions/site-section.md) 維度。 速記欄位 `data.__adobe.analytics.ch` 也受支援。 |
| `data.__adobe.analytics.colorDepth` | 此 [色彩深度](../../components/dimensions/color-depth.md) 維度。 速記欄位 `data.__adobe.analytics.c` 也受支援。 |
| `data.__adobe.analytics.connectionType` | 此 [連線型別](../../components/dimensions/connection-type.md) 維度。 速記欄位 `data.__adobe.analytics.ct` 也受支援。 |
| `data.__adobe.analytics.contextData` | [上下文資料變數](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | 此 [Cookie支援](../../components/dimensions/cookie-support.md) 維度。 速記欄位 `data.__adobe.analytics.k` 也受支援。 |
| `data.__adobe.analytics.currencyCode` | 此 [`currencyCode`](../vars/config-vars/currencycode.md) 實作變數。 速記欄位 `data.__adobe.analytics.cc` 也受支援。 |
| `data.__adobe.analytics.dynamicVariablePrefix` | 此 [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) 實作變數。 |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) 維度。 速記欄位 `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` 也受支援。 |
| `data.__adobe.analytics.events` | [自訂事件](../../components/metrics/custom-events.md). 格式化此欄位的方式與 [`events`](../vars/page-vars/events/events-overview.md) 實作變數。 |
| `data.__adobe.analytics.javaEnabled` | 此 [Java已啟用](../../components/dimensions/java-enabled.md) 維度。 速記欄位 `data.__adobe.analytics.v` 也受支援。 |
| `data.__adobe.analytics.latitude` | 協助設定 [位置](../../components/dimensions/lifecycle-dimensions.md) 行動生命週期維度。 速記欄位 `data.__adobe.analytics.lat` 也受支援。 |
| `data.__adobe.analytics.linkName` | 此 [自訂連](../../components/dimensions/custom-link.md)， [下載連](../../components/dimensions/download-link.md)，或 [退出連結](../../components/dimensions/exit-link.md) 維度，視中的值而定 `data.__adobe.analytics.linkType`. 速記欄位 `data.__adobe.analytics.pev2` 也受支援。 |
| `data.__adobe.analytics.linkURL` | 此 [`linkURL`](../vars/config-vars/linkurl.md) 實作變數。 速記欄位 `data.__adobe.analytics.pev1` 也受支援。 |
| `data.__adobe.analytics.linkType` | 判斷點擊的連結類型。有效值包括 `o` （自訂連結）， `d` （下載連結），以及 `e` （退出連結）。 速記欄位 `data.__adobe.analytics.pe` 也受支援。 |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) 實作變數。 速記欄位 `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` 也受支援。 |
| `data.__adobe.analytics.longitude` | 協助設定 [位置](../../components/dimensions/lifecycle-dimensions.md) 行動生命週期維度。 速記欄位 `data.__adobe.analytics.lon` 也受支援。 |
| `data.__adobe.analytics.pageName` | [頁面](/help/components/dimensions/page.md)維度。 |
| `data.__adobe.analytics.pageURL` | 此 [頁面URL](/help/components/dimensions/page-url.md) 維度。 速記欄位 `data.__adobe.analytics.g` 也受支援。 |
| `data.__adobe.analytics.pageType` | 此 [`pageType`](../vars/page-vars/pagetype.md) 實作變數。 |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) 維度。 速記欄位 `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` 也受支援。 |
| `data.__adobe.analytics.purchaseID` | 此 [`purchaseID`](../vars/page-vars/purchaseid.md) 實作變數。 |
| `data.__adobe.analytics.products` | 此 [`products`](../vars/page-vars/products.md) 實施變數，格式類似。 |
| `data.__adobe.analytics.referrer` | [反向連結](/help/components/dimensions/referrer.md)維度。 |
| `data.__adobe.analytics.resolution` | 此 [監視器解析度](../../components/dimensions/monitor-resolution.md) 維度。 速記欄位 `data.__adobe.analytics.s` 也受支援。 |
| `data.__adobe.analytics.server` | [伺服器](/help/components/dimensions/server.md)維度。 |
| `data.__adobe.analytics.tnta` | 用於A4T整合。 |
| `data.__adobe.analytics.transactionID` | 此 [`transactionID`](../vars/page-vars/transactionid.md) 實作變數。 速記欄位 `data.__adobe.analytics.xact` 也受支援。 |
| `data.__adobe.analytics.zip` | 此 [郵遞區號](../../components/dimensions/zip-code.md) 維度。 |

{style="table-layout:auto"}
