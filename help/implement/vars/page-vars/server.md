---
title: 伺服器
description: 填入「伺服器」維度。
feature: Appmeasurement Implementation
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/P0txq9O6mdXQ-avevETR0BTLRf3kQHAaN9HBFki8XKQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 82%

---

# 伺服器

`server` 變數通常會儲存網站的主機名稱。 它常用於包含多個網域資料的報表套裝。 它的功能與 prop 相同。

## 使用Web SDK的伺服器

伺服器已對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.web.webPageDetails.server`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.server`

## 使用Adobe Analytics擴充功能的伺服器

您可以在設定 Analytics 擴充功能 (全域變數) 時或是在規則底下設定伺服器。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設定為 Adobe Analytics，並將[!UICONTROL 「動作類型」]設定為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「伺服器」]區段。

您可以將伺服器設定為任何字串值或資料元素。

## AppMeasurement中的s.server與Analytics擴充功能自訂程式碼編輯器

`s.server` 變數是字串，通常包含網站的主機名稱。 其最大值為 100 個位元組；超過上限的值會遭到截斷。

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
