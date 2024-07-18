---
title: channel
description: 填入「網站區域」維度。
feature: Variables
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 75%

---

# channel

`channel` 變數通常會儲存指定頁面所在的網站區域。這個變數有助於判斷網站的哪些群組最受歡迎。此變數會填入「網站區域」維度。

## 使用Web SDK的管道

管道已對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `web.webPageDetails.siteSection`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.channel`或`data.__adobe.analytics.ch`

## 使用Adobe Analytics擴充功能的頻道

您可以在設定 Analytics 擴充功能 (全域變數) 時設定管道，或依據規則進行設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 擴充功能]下拉式清單設定為Adobe Analytics，並將[!UICONTROL 動作型別]設定為[!UICONTROL 設定變數]。
6. 找出[!UICONTROL 「管道」]區段。

您可以將管道設為任何字串值或資料元素。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.channel

`s.channel` 變數是字串，通常包含頁面的網站區域。其最大值為 100 個位元組；超過上限的值會遭到截斷。

```js
s.channel = "Example site section";
```

如果使用`digitalData` [資料層](../../prepare/data-layer.md)：

```js
s.channel = digitalData.page.category.primaryCategory;
```
