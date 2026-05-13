---
title: channel
description: 填入「網站區域」維度。
feature: Appmeasurement Implementation
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
TQID: https://experienceleague.adobe.com/hctVvVL98TCC2y6dUvO-5jhO40CkYwRB8ygBUcWu684
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 198
ht-degree: 83%

---

# channel

`channel` 變數通常會儲存指定頁面所在的網站區域。 這個變數有助於判斷網站的哪些群組最受歡迎。 此變數會填入「網站區域」維度。

## 使用網頁SDK的管道

管道已對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `web.webPageDetails.siteSection`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.channel`或`data.__adobe.analytics.ch`

## 使用Adobe Analytics擴充功能的頻道

您可以在設定 Analytics 擴充功能 (全域變數) 時設定管道，或依據規則進行設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設定為 Adobe Analytics，並將[!UICONTROL 「動作類型」]設定為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「管道」]區段。

您可以將管道設為任何字串值或資料元素。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.channel

`s.channel` 變數是字串，通常包含頁面的網站區域。 其最大值為 100 個位元組；超過上限的值會遭到截斷。

```js
s.channel = "Example site section";
```

如果使用`digitalData` [資料層](../../prepare/data-layer.md)：

```js
s.channel = digitalData.page.category.primaryCategory;
```
