---
title: 州別
description: 在 Reports and Analytics 中填入「訪客州報表」。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 州別

>[!IMPORTANT] 此變數已遭到淘汰，在 Analysis Workspace 中不是可用維度。請改用「美國州」維度；AppMeasurement 會根據訪客的位置自動收集該維度。

在舊版 Adobe Analytics 中，當訪客在零售網站上填寫運送資訊時，會使用 `state` 變數。它的功能與 prop 相同，不過在 Analysis Workspace 中無法使用。

## Adobe Experience Platform Launch 中的州

您可以在設定 Analytics 擴充功能 (全域變數) 時設定州，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. 在下 [!UICONTROL Actions]方，按一下現 [!UICONTROL Adobe Analytics - Set Variables] 有動作或按一下「+」圖示。
5. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為 [!UICONTROL Set Variables]。
6. Locate the [!UICONTROL State] section.

您可以將州設定為任何字串值或資料元素。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.state

`s.state` 變數是字串，通常包含訪客的州或省。完整的州名或雙字母代碼都是有效值。其最大值為 50 個位元組；超過上限的值會遭到截斷。其預設值為空字串。

```js
s.state = "Utah";
```
