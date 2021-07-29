---
title: channel
description: 填入「網站區域」維度。
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 87%

---

# 頻道

`channel` 變數通常會儲存指定頁面所在的網站區域。這個變數有助於判斷網站的哪些群組最受歡迎。此變數會填入「網站區域」維度。

## 在Adobe Experience Platform中使用標籤的管道

您可以在設定 Analytics 擴充功能 (全域變數) 時設定頻道，或依據規則進行設定。

1. 使用您的AdobeID憑證登入[資料收集UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「頻道」]區段。

您可以將頻道設為任何字串值或資料元素。

## AppMeasurement 和 自訂程式碼編輯器中的 s.channel

`s.channel` 變數是字串，通常包含頁面的網站區域。其最大值為 100 個位元組；超過上限的值會遭到截斷。

```js
s.channel = "Example site section";
```

如果使用`digitalData` [資料層](../../prepare/data-layer.md)：

```js
s.channel = digitalData.page.category.primaryCategory;
```
