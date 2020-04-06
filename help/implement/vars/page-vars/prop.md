---
title: prop
description: 可在實施中使用的自訂變數。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# prop

prop 是自訂變數，您可以視需要使用。

>[!TIP] Adobe 建議在大部分情況下使用 eVar。在舊版 Adobe Analytics 中，prop 和 eVar 各有其優缺點。不過 Adobe 已改良 eVar，現在它們幾乎能完成 prop 的所有使用案例。如需這兩種自訂變數類型的功能比較，請參閱 [eVar](evar.md)。

如果貴組織使用 prop，請務必將其使用方法與邏輯記錄在[解決方案設計文件](../../prepare/solution-design.md)中。

## Adobe Experience Platform Launch 中的 prop

您可以在設定 Analytics 擴充功能 (全域變數) 時設定 prop，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. 在下 [!UICONTROL Actions]方，按一下現 [!UICONTROL Adobe Analytics - Set Variables] 有動作或按一下「+」圖示。
5. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為 [!UICONTROL Set Variables]。
6. Locate the [!UICONTROL Props] section.

您可以選取 prop 來設定值或資料元素。您也可以複製其他 Analytics 變數的值。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.prop1 - s.prop75

每個 prop 變數都是字串，其中包含貴組織專屬的自訂值。它們的最大長度為 100 個位元組；超過 100 個位元組的值會在傳送至 Adobe 時自動截斷。

```js
s.prop1 = "Example custom value";
```

## 清單屬性

清單屬性是套用至 prop 的設定，可讓變數在同一次點擊中保留多個值。如果未啟用此設定或使用錯誤的分隔字元，系統會將變數視為單一值。

### 設定清單屬性

在報表套裝設定中啟用清單屬性。請參閱「管理員使用指南」中的[流量變數](/help/admin/admin/c-traffic-variables/traffic-var.md)。請確認所需的分隔字元已正確設定。Adobe 不提供預設分隔字元。

>[!TIP] 實施中常用的分隔字元包括逗號 (`,`)、冒號 (`:`)、分號 (`;`) 或垂直號 (`|`)。您可以使用最符合實施需求的分隔字元。

### 設定清單屬性

在報表套裝設定中設定清單屬性的所需分隔字元後，除了使用分隔字元外，在實施上沒有任何差異。

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT] 清單屬性仍有最多 100 個位元組的長度限制。清單屬性很容易因達到此限制而遭到截斷，因為它們可以包含多個值。如果您可能會達到前述 100 個位元組的限制，請考慮使用縮寫或縮短值。

如果您在清單prop中設定相同值多次，則會在報表中消除重複資料。 「分析工作區」會計算檢視值的點擊數，而非資料中值存在的次數。
