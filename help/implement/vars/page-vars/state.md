---
title: 州別
description: （已淘汰）填入無法再使用的「訪客州報表」。
feature: Appmeasurement Implementation
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 80%

---

# 州別

>[!IMPORTANT]
>
>此變數已遭到淘汰，在 Analysis Workspace 中不是可用維度。請改用[美國州](/help/components/dimensions/us-states.md)維度，AppMeasurement會根據訪客的位置自動收集該維度。

在舊版 Adobe Analytics 中，當訪客在零售網站上填寫運送資訊時，會使用 `state` 變數。它的功能與 prop 相同，不過在 Analysis Workspace 中無法使用。

## 使用 Adobe Analytics 擴充功能的州

您可以在設定 Analytics 擴充功能 (全域變數) 時或是在規則底下設定狀態。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 擴充功能]下拉式清單設定為Adobe Analytics，並將[!UICONTROL 動作型別]設定為[!UICONTROL 設定變數]。
6. 找出[!UICONTROL 「州」]區段。

您可以將州設定為任何字串值或資料元素。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.state

`s.state` 變數是字串，通常包含訪客的州或省。完整的州名或雙字母代碼都是有效值。其最大值為 50 個位元組；超過上限的值會遭到截斷。其預設值為空字串。

```js
s.state = "Utah";
```
