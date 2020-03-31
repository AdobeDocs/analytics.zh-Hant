---
title: eVar
description: 可在實施中使用的自訂變數。
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# eVar

*此說明頁面說明如何實作eVar。 如需eVar如何作為維度運作的詳細資訊，請參[閱「元件](../../../components/c-variables/dimensionslist/reports-conversion.md)」使用指南中的eVar。*

eVar 是自訂變數，您可以視需要使用。

> [!TIP] Adobe 建議您在大部分情況下使用 eVar 來取代 prop。在舊版 Adobe Analytics 中，prop 和 eVar 各有其優缺點。不過 Adobe 已改良 eVar，現在它們幾乎能完成 prop 的所有使用案例。

請務必將每個 eVar 的使用方式與其邏輯記錄在[解決方案設計文件](../../prepare/solution-design.md)內。

## 在報表套裝設定中設定 eVar

在實施中使用 eVar 之前，請務必在報表套裝設定中設定每個 eVar。請參閱「管理員指南」中的[轉換變數](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。

## Adobe Experience Platform Launch 中的 eVar

您可以在設定 Analytics 擴充功能 (全域變數) 時設定 eVar，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. 在下 [!UICONTROL Actions]方，按一下現 [!UICONTROL Adobe Analytics - Set Variables] 有動作或按一下「+」圖示。
5. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為 [!UICONTROL Set Variables]。
6. Locate the [!UICONTROL eVars] section.

您可以選取 eVar 來設定值或資料元素。您也可以複製其他 Analytics 變數的值。

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

> [!IMPORTANT] 您必須先在管理控制台中將eVar設定為&#39;Counter&#39;，才能使用計數器eVar。 請參閱「管理員指南」中的[轉換變數](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。

## prop 或 eVar 的獨特優點

在目前的 Adobe Analytics 版本中，prop 和 eVar 都是具有類似功能的自訂變數。儘管如此，兩者之間還是有幾項重大差異：

* prop 中的資料可在數分鐘內供報表使用。eVar 可能需要 30 分鐘以上才會出現在報表中。
* prop 在報表中的長度限制為 100 個位元組。eVar 的長度限制為 255 個位元組。
* prop 可成為清單屬性，這些 prop 能在同一次點擊中接受多個值。清單變數是個別的變數，而且只有三個清單變數可供使用。
* 依預設，prop 不會持續存在超過設定的點擊。eVar 有自訂的過期時間，可讓您判斷 eVar 何時不再獲得後續事件的評分。不過，如果您使用報 [告時間處理](../../../components/vrs/vrs-report-time-processing.md),prop和eVar都可以使用自訂歸因模型。
