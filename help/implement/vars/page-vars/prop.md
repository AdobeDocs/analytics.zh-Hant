---
title: prop
description: 可在實施中使用的自訂變數。
feature: Appmeasurement Implementation
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 85%

---

# prop

*此說明頁面說明如何實施作業 Prop。若要瞭解 Prop 作為維度時的運作方式，請參閱「元件」使用指南中的 [Prop](/help/components/dimensions/prop.md)。*

Prop 是自訂變數，您可以視需要使用。這類變數在其設定所在的點擊過後即不存在。

>[!TIP]
>
>Adobe 建議在大部分情況下使用 [eVar](evar.md)。在舊版 Adobe Analytics 中，prop 和 eVar 各有其優缺點。不過Adobe已大幅改善eVar，現在幾乎能完成prop的所有使用案例。

如果您有[解決方案設計文件](/help/implement/prepare/solution-design.md)，您可以將這些自訂維度配置給組織的特定值。可用的 Prop 數量取決於您與 Adobe 訂定的合約。在您的 Adobe 合約支援的前提下，最多可使用 75 個 Prop。

## 使用 Web SDK 的屬性

Prop會對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm._experience.analytics.customDimensions.props.prop1` - `xdm._experience.analytics.customDimensions.props.prop75` — 清單屬性是在[獨立的欄位集](#list-props-web-sdk)中指定的。
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75`；或`data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` — 清單屬性包含在這些欄位中。

## 使用 Adobe Analytics 擴充功能的屬性

您可以在設定 Analytics 擴充功能 (全域變數) 時設定 prop，或依據規則進行設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 擴充功能]下拉式清單設定為Adobe Analytics，並將[!UICONTROL 動作型別]設定為[!UICONTROL 設定變數]。
6. 找出[!UICONTROL 「prop」]區段。

您可以將 Prop 設為一個值或資料元素。您也可以複製其他 Analytics 變數的值。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.prop1 - s.prop75

每個 prop 變數都是字串，其中包含貴組織專屬的自訂值。它們的最大長度為 100 個位元組；超過 100 個位元組的值會在傳送至 Adobe 時自動截斷。

```js
s.prop1 = "Example custom value";
```

## 清單屬性

清單屬性是套用至 prop 的設定，可讓變數在同一次點擊中保留多個值。如果未啟用此設定或使用錯誤的分隔字元，系統會將變數視為單一值。

### 設定清單屬性

在報表套裝設定下的[流量變數](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)中啟用清單屬性。請確認所需的分隔字元已正確設定。Adobe 不提供預設分隔字元。

>[!TIP]
>
> 實施作業中常用的分隔字元包括逗號 (`,`)、冒號 (`:`)、分號 (`;`) 或垂直號 (`|`)。您可以使用最符合實施需求的非加強式 ASCII。

### 使用 Web SDK 設定清單變數 {#list-props-web-sdk}

如果使用&#x200B;[**XDM物件**](/help/implement/aep-edge/xdm-var-mapping.md)，清單屬性會對應至`xdm._experience.analytics.customDimensions.listProps.prop1.values[]` - `xdm._experience.analytics.customDimensions.listProps.prop75.values[]`。 Web SDK 會自動使用報表套裝設定下所列的正確分隔字元。 如果您在 XDM 欄位中設定分隔字元 (例如，`xdm._experience.analytics.customDimensions.props.prop1.delimiter`)，該分隔字元會覆寫從報表套裝設定中自動擷取的分隔字元，並可能導致清單屬性串的剖析不正確。

如果使用&#x200B;[**資料物件**](/help/implement/aep-edge/data-var-mapping.md)，則清單prop會使用與標準prop相同的欄位，並遵循AppMeasurement語法。

### 使用 Adobe Analytics 擴充功能和 AppMeasurement 來設定清單屬性

在報表套裝設定中設定清單屬性的所需分隔字元後，除了使用分隔字元外，在實施上沒有任何差異。

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
>清單屬性仍有最多 100 個位元組的長度限制。清單屬性很容易因達到此限制而遭到截斷，因為它們可以包含多個值。如果您可能會達到前述 100 個位元組的限制，請考慮使用縮寫或縮短值。

如果您在清單屬性中設定相同值多次，系統會在報表中刪除重複資料。Analysis Workspace 會計算檢視值處的點擊數，而非資料中值存在的次數。
