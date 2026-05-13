---
title: pageURL
description: 覆寫在網站上自動收集的頁面 URL。
feature: Appmeasurement Implementation
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
role: Admin, Developer
TQID: https://experienceleague.adobe.com/DZM2tZlfVX0g9OYMj6tPFuHInBZdBrboJ4vGz16Lfrs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 310
ht-degree: 84%

---

# pageURL

AppMeasurement 會自動收集每次點擊中的頁面 URL。 如果您想要覆寫 AppMeasurement 自動收集的頁面 URL，可以使用此變數。 在大多數情況下，您不需要設定此變數。

>[!NOTE]
>
>此變數不是 Analysis Workspace 中的可用維度。 它僅適用於 Data Warehouse 和資料摘要。 此外，Adobe 資料收集伺服器會從所有 [連結追蹤](/help/implement/vars/functions/tl-method.md) 影像要求中移除此維度。 如果您想要在 Analysis Workspace 中將頁面 URL 當做維度，或想在連結追蹤點擊中使用此維度，請考慮在每次點擊時`pageURL`將變數傳入 [eVar](evar.md)。

## 使用網頁SDK的頁面URL

頁面URL已對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.web.webPageDetails.URL`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.pageURL`或`data.__adobe.analytics.g`

## 使用Adobe Analytics擴充功能的頁面URL

Adobe Experience Platform Data Collection中的Analytics擴充功能會自動填入頁面URL。 不過，您可以在設定 Analytics 擴充功能 (全域變數) 時設定頁面 URL 覆寫，或依據規則進行設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往&#x200B;**[!UICONTROL 規則]**&#x200B;標籤，然後按一下所需的規則 (或建立規則)。
4. 在&#x200B;**[!UICONTROL 「動作」]**&#x200B;下方按一下現有的&#x200B;**[!UICONTROL 「Adobe Analytics - 設定變數」]**&#x200B;動作，或按一下「+」圖示。
5. 將&#x200B;**[!UICONTROL 「擴充功能」]**&#x200B;下拉式清單設定為 Adobe Analytics，並將&#x200B;**[!UICONTROL 「動作類型」]**&#x200B;設定為&#x200B;**[!UICONTROL 「設定變數」]**。
6. 找出&#x200B;**[!UICONTROL 「頁面 URL」]**&#x200B;區段。

您可以將頁面 URL 設為任何字串值。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.pageURL

`s.pageURL` 變數是包含頁面 URL 的字串。 AppMeasurement 會自動收集此變數，不過您可以視需要覆寫其值。

```js
s.pageURL = "https://example.com";
```

如果您想要將頁面 URL 當做報表中的維度，請考慮在實施中使用下列項目：

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

如果使用`digitalData` [資料層](../../prepare/data-layer.md)：

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
