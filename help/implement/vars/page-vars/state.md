---
title: 州別
description: 在 Reports and Analytics 中填入「訪客州報表」。
translation-type: ht
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# 州別

> [!IMPORTANT] 此變數已遭到淘汰，在 Analysis Workspace 中不是可用維度。請改用「美國州」維度；AppMeasurement 會根據訪客的位置自動收集該維度。

在舊版 Adobe Analytics 中，當訪客在零售網站上填寫運送資訊時，會使用 `state` 變數。它的功能與 prop 相同，不過在 Analysis Workspace 中無法使用。

## Adobe Experience Platform Launch 中的州

您可以在設定 Analytics 擴充功能 (全域變數) 時設定州，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「州」]區段。

您可以將州設定為任何字串值或資料元素。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.state

`s.state` 變數是字串，通常包含訪客的州或省。完整的州名或雙字母代碼都是有效值。其最大值為 50 個位元組；超過上限的值會遭到截斷。其預設值為空字串。

```js
s.state = "Utah";
```
