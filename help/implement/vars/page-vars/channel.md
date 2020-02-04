---
title: channel
description: 填入「網站區域」維度。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# channel

變 `channel` 數通常會儲存指定頁面所在的網站區段。 確定您網站的哪些群組最受歡迎是很有幫助的。 此變數會填入「網站區域」維度。

## Adobe Experience Platform Launch的頻道

您可以在設定Analytics擴充功能（全域變數）時或在規則下設定渠道。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下方，按一下現有  的Adobe Analytics - 「設定變數」動作，或按一下「+」圖示。
5. 將「延伸 [!UICONTROL 功能] 」下拉式清單設定為Adobe Analytics，並將「動作類型 [!UICONTROL 」設] 定為變數 。
6. 找到「 [!UICONTROL Channel] 」部分。

您可以將channel設為任何字串值或資料元素。

## AppMeasurement和Launch自訂代碼編輯器中的s.channel

變 `s.channel` 數是一個字串，通常包含頁面的網站區段。 其最大值為100個位元組；較長的值會被截斷。

```js
s.channel = "Example site section";
```
