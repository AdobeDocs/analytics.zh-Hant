---
title: transactionID
description: 使用此變數可將線上和離線資料連結在一起。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# transactionID

變 `transactionID` 數可唯一識別交易，因此點擊可關聯至透過Data Sources上傳的資料。 若您想要使用其他渠道的資料並將其連結至透過AppMeasurement收集的資料，此變數很有用。

> [!NOTE] 使用此變  數前，請確定報表套裝中已啟用「交易ID儲存」。 See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

當您設 `transactionID` 定點擊時，Adobe會對所有Analytics變數集進行「快照」，或保留在該時間點。 透過具有相符交易ID的Data Sources上傳的資料會永久系結至這些變數值。

依預設，Adobe會記住最多90天的所有交易ID值（連結和未連結）。 如果您的離線互動程式超過90天，請聯絡客戶服務以延長此限制。

## Adobe Experience Platform Launch中的交易ID

您可以在設定Analytics擴充功能（全域變數）時或在規則下設定交易ID。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下方，按一下現有  的Adobe Analytics - 「設定變數」動作，或按一下「+」圖示。
5. 將「延伸 [!UICONTROL 功能] 」下拉式清單設定為Adobe Analytics，並將「動作類型 [!UICONTROL 」設] 定為變數 。
6. 找到「 [!UICONTROL 交易ID] 」區段。

您可以將交易ID設為任何字串值，包括資料元素。

## AppMeasurement和Launch自訂代碼編輯器中的s.transactionID

變 `s.transactionID` 數是包含交易唯一識別碼的字串。 有效值包括長度高達100個位元組的英數字元。 其預設值為空字串。

```js
s.transactionID = "ABC123";
```

如果您有多個點擊交易ID，則可以用逗號分隔每個交易ID。 多個交易ID仍受100位元組限制。

```js
s.transactionID = "ABC123,XYZ456";
```

> [!NOTE] 如果您使用此變數整合多個離線渠道，請確定不同渠道不會重疊交易ID。 例如，如果您的話務中心交易ID值為，而 `1234` 銷售線索交易ID值為 `1234`，則可能發生衝突並導致意外結果。 請確定交易ID包含每個離線渠道的唯一格式，並視需要加以區隔。 例如，在Data Sources和AppMeasurement中，將您的話務中心交易ID設 `call_1234` 定為和您的銷售 `lead_1234` 線索交易ID。
