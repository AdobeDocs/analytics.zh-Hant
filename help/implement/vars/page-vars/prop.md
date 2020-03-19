---
title: prop
description: 您可在實作中使用的自訂變數。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# prop

Prop是自訂變數，您可以視需要使用。

> [!TIP] Adobe建議在大部分情況下使用eVar。 在舊版Adobe Analytics中，prop和eVar有其優缺點。 不過，Adobe已將eVar改良為幾乎可完成所有prop使用案例的eVar。 請參 [閱eVar](evar.md) ，以取得這兩種自訂變數類型的功能比較。

如果您的組織使用prop，請務必在解決方案設計檔案中記錄其使 [用和邏輯](../../prepare/solution-design.md)。

## Adobe Experience Platform Launch中的Prop

您可以在設定Analytics擴充功能（全域變數）時或在規則下設定prop。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Rules] ，然後按一下所要的規則（或建立規則）。
4. 在下 [!UICONTROL Actions]方，按一下現 [!UICONTROL Adobe Analytics - Set Variables] 有動作或按一下「+」圖示。
5. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為 [!UICONTROL Set Variables]。
6. Locate the [!UICONTROL Props] section.

您可以選取prop來設定值或資料元素。 您也可以從其他Analytics變數複製值。

## s.prop1 - AppMeasurement和Launch自訂代碼編輯器中的s.prop75

每個prop變數都是包含您組織專屬之自訂值的字串。 最大長度為100個位元組；超過100位元組的值會在傳送至Adobe時自動截斷。

```js
s.prop1 = "Example custom value";
```

## 列出prop

清單prop是套用至prop的設定，可讓變數在相同點擊中保留多個值。 如果未啟用此設定，或使用錯誤的分隔字元，則變數會視為單一值。

### 設定清單prop

在報表套裝設定中啟用清單prop。 See [Traffic variables](/help/admin/admin/c-traffic-variables/traffic-var.md) in the Admin user guide. 請確定所要的分隔字元已正確設定。 Adobe不提供預設分隔字元。

> [!TIP] 實作中使用的常見分隔字元是逗號(`,`)、冒號(`:`)、分號(`;`)或垂直號(`|`)。 您可以使用最適合您實作的分隔字元。

### 設定清單prop

在報表套裝設定中設定具有所需分隔字元的清單prop後，除了使用分隔字元外，沒有實作差異。

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

> [!IMPORTANT] 清單prop仍受100位元組最大長度的限制。 清單prop可以更容易達到此限制並遭截斷，因為它們可以包含多個值。 如果您可能達到此100位元組限制，請考慮使用縮寫或縮短值。

如果您在清單prop中設定相同值多次，則會在報表中消除重複資料。 「分析工作區」會計算檢視值的點擊數，而非資料中值存在的次數。
