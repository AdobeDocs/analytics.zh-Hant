---
title: eVar
description: 可在實施中使用的自訂變數。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 86%

---


# eVar

*此說明頁面說明如何實施 eVar。如需 eVar 如何當作維度的詳細資訊，請參閱元件使用手冊中的[eVar](/help/components/dimensions/evar.md)。*

eVar 是自訂變數，您可以視需要使用。如果您有[解決方案設計文件](/help/implement/prepare/solution-design.md)，則貴組織的大部分特定維度最終都會變成 eVar。依預設，eVar 可存留於其設定的點擊之外。You can customize their expiration and allocation under [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in Report suite settings.

可用eVar的數量視您與Adobe的合約而定。 若您與Adobe的合約支援，則最多可使用250個eVar。

## 在報表套裝設定中設定 eVar

在實施中使用 eVar 之前，請務必在報表套裝設定中設定每個 eVar。請參閱「管理員指南」中的[轉換變數](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。

## Adobe Experience Platform Launch 中的 eVar

您可以在設定 Analytics 擴充功能 (全域變數) 時設定 eVar，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「eVar」]區段。

您可以將eVar設為值或資料元素。 您也可以複製其他 Analytics 變數的值。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.eVar1 - s.eVar250

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
> 您必須先在 Admin Console 中將 eVar 設為「計數器」，才能使用計數器 eVar。請參閱「管理員指南」中的[轉換變數](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。
