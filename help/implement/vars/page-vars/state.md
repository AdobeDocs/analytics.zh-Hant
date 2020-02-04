---
title: 狀態
description: 在「報表與分析」中填入「訪客狀態報表」。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# state

> [!IMPORTANT] 此變數會停用，而不是分析工作區中的可用維度。 請改用「美國州」維度，AppMeasurement會根據訪客的位置自動收集該維度。

在舊版Adobe Analytics中，訪客填 `state` 寫零售網站的運送資訊時，會使用此變數。 它在功能上與prop相同，但在「分析工作區」中不可用。

## Adobe Experience Platform Launch的狀態

您可以在設定Analytics擴充功能（全域變數）時或在規則下設定狀態。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下方，按一下現有  的Adobe Analytics - 「設定變數」動作，或按一下「+」圖示。
5. 將「延伸 [!UICONTROL 功能] 」下拉式清單設定為Adobe Analytics，並將「動作類型 [!UICONTROL 」設] 定為變數 。
6. 找到「 [!UICONTROL State] （狀態）」部分。

您可以將狀態設定為任何字串值或資料元素。

## AppMeasurement和Launch自訂代碼編輯器中的s.state

變 `s.state` 數是字串，通常包含訪客的州或省。 完整狀態名稱或雙字母代碼都有效。 其最大值為50個位元組；較長的值會被截斷。 其預設值為空字串。

```js
s.state = "Utah";
```
