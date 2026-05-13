---
title: 州別
description: （已淘汰）填入無法再使用的「訪客州報表」。
feature: Appmeasurement Implementation
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
role: Admin, Developer
TQID: https://experienceleague.adobe.com/3GhnJJj6gxEt0Qiefd4siS6-YzDbOw4hdY4IsNhwYDU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 230
ht-degree: 87%

---

# 州別

>[!IMPORTANT]
>
>此變數已遭到淘汰，在 Analysis Workspace 中不是可用維度。 請改用[美國州](/help/components/dimensions/us-states.md)維度，AppMeasurement會根據訪客的位置自動收集該維度。

在舊版 Adobe Analytics 中，當訪客在零售網站上填寫運送資訊時，會使用 `state` 變數。 它的功能與 prop 相同，不過在 Analysis Workspace 中無法使用。

## 使用 Adobe Analytics 擴充功能的州

您可以在設定 Analytics 擴充功能 (全域變數) 時或是在規則底下設定狀態。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設定為 Adobe Analytics，並將[!UICONTROL 「動作類型」]設定為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「州」]區段。

您可以將州設定為任何字串值或資料元素。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.state

`s.state` 變數是字串，通常包含訪客的州或省。 完整的州名或雙字母代碼都是有效值。 其最大值為 50 個位元組；超過上限的值會遭到截斷。 其預設值為空字串。

```js
s.state = "Utah";
```
