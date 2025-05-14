---
title: transactionID
description: 此變數可用來將線上和離線資料連結在一起。
feature: Variables
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
role: Admin, Developer
source-git-commit: 43035967e8ccbb35700b7ad3e893282ade310acd
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 89%

---

# transactionID

`transactionID` 變數可唯一識別交易，因此點擊能與透過 Data Sources 上傳的資料連結。若您想要使用其他管道的資料，並將這些資料與透過 AppMeasurement 收集的資料連結在一起，此變數很有用。

>[!NOTE]
>
>使用此變數之前，請確認報表套裝中的[!UICONTROL 「交易 ID 儲存」]已啟用。如需詳細資訊，請參閱「管理員使用指南」中的[一般帳戶設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)。

當您在點擊上設定 `transactionID` 時，Adobe 會針對在該時間點設定或留存的所有 Analytics 變數拍攝「快照」。透過 Data Sources 上傳且具有相符交易 ID 的資料會永遠與這些變數值連結。

Adobe最多可記住25個月的所有交易ID值（連結和未連結）。

## 使用 Web SDK 的交易 ID

交易ID會對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.commerce.order.payments[3].transactionID`或`xdm.commerce.order.payments.transactionID`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.transactionID`或`data.__adobe.analytics.xact`

## 使用 Adobe Analytics 擴充功能的交易 ID

您可以在設定 Analytics 擴充功能 (全域變數) 時設定交易 ID，或依據規則進行設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 擴充功能]下拉式清單設定為Adobe Analytics，並將[!UICONTROL 動作型別]設定為[!UICONTROL 設定變數]。
6. 找出[!UICONTROL 「交易 ID」]區段。

您可以將交易 ID 設為任何字串值，包括資料元素。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.transactionID

`s.transactionID` 變數是包含交易唯一識別碼的字串。有效值包括長度最多 100 個位元組的英數字元。其預設值為空字串。

```js
s.transactionID = "ABC123";
```

如果您的點擊有多個交易 ID，可以使用逗號分隔每個 ID。即使有多個交易 ID，長度上限仍是 100 個位元組。

```js
s.transactionID = "ABC123,XYZ456";
```

>[!TIP]
>
>如果您使用此變數整合多個離線管道，請確認不同管道之間沒有重疊的交易 ID。例如，如果您的呼叫中心交易 ID 值為 `1234`，潛在客戶交易 ID 值為 `1234`，可能會發生衝突並導致意外結果。請確認每個離線管道的交易 ID 均包含唯一格式，並視需要加以區分。例如，在 Data Sources 和 AppMeasurement 中，將呼叫中心交易 ID 設定為 `call_1234`，將潛在客戶交易 ID 設定為 `lead_1234`。
