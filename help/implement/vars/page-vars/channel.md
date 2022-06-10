---
title: channel
description: 填入「網站區域」維度。
feature: Variables
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 74%

---

# 通道

`channel` 變數通常會儲存指定頁面所在的網站區域。這個變數有助於判斷網站的哪些群組最受歡迎。此變數會填入「網站區域」維度。

## 使用Web SDK的通道

通道是 [映射為Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 在XDM欄位下 `web.webPageDetails.siteSection`。

## 使用Adobe Analytics擴展的頻道

您可以在設定 Analytics 擴充功能 (全域變數) 時設定管道，或依據規則進行設定。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
2. 按一下所需的標記屬性。
3. 前往[!UICONTROL 規則]標記，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「管道」]區段。

您可以將管道設為任何字串值或資料元素。

## AppMeasurement中的s.channel和Analytics擴展自定義代碼編輯器

`s.channel` 變數是字串，通常包含頁面的網站區域。其最大值為 100 個位元組；超過上限的值會遭到截斷。

```js
s.channel = "Example site section";
```

如果使用`digitalData` [資料層](../../prepare/data-layer.md)：

```js
s.channel = digitalData.page.category.primaryCategory;
```
