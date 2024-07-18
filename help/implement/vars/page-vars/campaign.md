---
title: 促銷活動
description: 填入「追蹤程式碼」維度。
feature: Variables
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 88%

---

# 促銷活動

`campaign` 變數專用於收集網站上的追蹤程式碼。在舊版 Adobe Analytics 中，它有特殊處理方式，可用來劃分大部分維度。在目前版本的 Adobe Analytics 中，其作用與 eVar 相同。

此變數會填入[追蹤程式碼](/help/components/dimensions/tracking-code.md)維度。 它通常使用 [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) 公用程式方法從查詢字串獲取其值。 然而，您的組織可確切地決定如何設定此變數。

## 使用 Web SDK 的行銷活動

Campaign會對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `marketing.trackingCode`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.campaign`或`data.__adobe.analytics.v0`

## 使用 Adobe Analytics 擴充功能的行銷活動

您可以在設定 Analytics 擴充功能 (全域變數) 時或是在規則底下設定行銷活動。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 擴充功能]下拉式清單設定為Adobe Analytics，並將[!UICONTROL 動作型別]設定為[!UICONTROL 設定變數]。
6. 找出[!UICONTROL 「促銷活動」]區段。

您可以將促銷活動設為值或查詢字串參數。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.campaign

`s.campaign` 變數是字串，通常包含行銷工作中使用的追蹤程式碼。 最大長度為 255 個位元組；超過 255 個位元組的值會在傳送至 Adobe 時自動截斷。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
