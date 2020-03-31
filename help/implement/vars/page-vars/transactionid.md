---
title: transactionID
description: 此變數可用來將線上和離線資料連結在一起。
translation-type: ht
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# transactionID

`transactionID` 變數可唯一識別交易，因此點擊能與透過 Data Sources 上傳的資料連結。若您想要使用其他頻道的資料，並將這些資料與透過 AppMeasurement 收集的資料連結在一起，此變數很有用。

> [!NOTE] 使用此變數之前，請確認報表套裝中的[!UICONTROL 「交易 ID 儲存」]已啟用。如需詳細資訊，請參閱「管理員使用指南」中的[一般帳戶設定](/help/admin/admin/general-acct-settings-admin.md)。

當您在點擊上設定 `transactionID` 時，Adobe 會針對在該時間點設定或留存的所有 Analytics 變數拍攝「快照」。透過 Data Sources 上傳且具有相符交易 ID 的資料會永遠與這些變數值連結。

依預設，Adobe 會記住所有交易 ID 值 (連結和未連結) 達 90 天。如果您的離線互動程序超過 90 天，請聯絡客戶服務以要求延長期限。

## Adobe Experience Platform Launch 中的交易 ID

您可以在設定 Analytics 擴充功能 (全域變數) 時設定交易 ID，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「交易 ID」]區段。

您可以將交易 ID 設為任何字串值，包括資料元素。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.transactionID

`s.transactionID` 變數是包含交易唯一識別碼的字串。有效值包括長度最多 100 個位元組的英數字元。其預設值為空字串。

```js
s.transactionID = "ABC123";
```

如果您的點擊有多個交易 ID，可以使用逗號分隔每個 ID。即使有多個交易 ID，長度上限仍是 100 個位元組。

```js
s.transactionID = "ABC123,XYZ456";
```

> [!NOTE] 如果您使用此變數整合多個離線頻道，請確認不同頻道之間沒有重疊的交易 ID。例如，如果您的呼叫中心交易 ID 值為 `1234`，潛在客戶交易 ID 值為 `1234`，可能會發生衝突並導致意外結果。請確認每個離線頻道的交易 ID 均包含唯一格式，並視需要加以區分。例如，在 Data Sources 和 AppMeasurement 中，將呼叫中心交易 ID 設定為 `call_1234`，將潛在客戶交易 ID 設定為 `lead_1234`。
