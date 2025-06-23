---
title: eVar (變數)
description: 可在實施中使用的自訂變數。
feature: Appmeasurement Implementation
exl-id: f89457b2-4186-4276-8637-9992070e3a73
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 92%

---

# eVar

*此說明頁面說明如何實施 eVar。如需 eVar 如何當作維度的詳細資訊，請參閱元件使用手冊中的 [eVar](/help/components/dimensions/evar.md)。*

eVar 是自訂變數，您可以視需要使用。如果您有[解決方案設計文件](/help/implement/prepare/solution-design.md)，則貴組織的大部分特定維度最終都會變成 eVar。依預設，eVar 可存留於其設定的點擊之外。您可以在報告套裝設定中的[「轉換變數」](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)下自訂其期限和配置。

可用的 eVar 數量取決於您與 Adobe 訂定的合約。在您的 Adobe 合約支援的前提下，最多可使用 250 個 eVar。

## 在報表套裝設定中設定 eVar

在實作中使用 eVar 之前，請務必在報表套裝設定中設定每個 eVar。請參閱「管理員指南」中的[轉換變數](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)。

## 使用 Web SDK 的 eVar

eVar會對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm._experience.analytics.customDimensions.eVars.eVar1`至`xdm._experience.analytics.customDimensions.eVars.eVar250`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.eVar1`至`data.__adobe.analytics.eVar250`；或`data.__adobe.analytics.v1`至`data.__adobe.analytics.v250`

## 使用 Adobe Analytics 擴充功能的 eVar

您可以在設定 Analytics 擴充功能 (全域變數) 時設定 eVar，或依據規則進行設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 擴充功能]下拉式清單設定為Adobe Analytics，並將[!UICONTROL 動作型別]設定為[!UICONTROL 設定變數]。
6. 找出[!UICONTROL 「eVar」]區段。

您可以將 eVar 設為一個值或資料元素。您也可以複製其他 Analytics 變數的值。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.eVar1 - s.eVar250

每個 eVar 都是字串，其中包含貴組織專屬的自訂值。它們的最大長度為 255 個位元組；超過 255 個位元組的值會在傳送至 Adobe 時自動截斷。

```js
s.eVar1 = "Example custom value";
```

## 計數器 eVar

eVar 值通常包含字串值。不過您可以設定 eVar，改為包含計數器。例如，您想要計算購買前進行的內部搜尋數目。建議您使用下列語法，避免設定文字值：

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

若指定了兩個以上的小數位數，eVar 計數器會進位至兩個小數位數。eVar 計數器不能包含負數。

>[!IMPORTANT]
>
>您必須先在 Admin Console 中將 eVar 設為「計數器」，才能使用計數器 eVar。請參閱「管理員指南」中的[轉換變數](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)。
