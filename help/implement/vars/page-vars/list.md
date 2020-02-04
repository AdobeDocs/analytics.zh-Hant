---
title: list
description: 在相同點擊中包含多個值的自訂變數。
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# list

清單變數是自訂變數，您可以視需要使用。 它們的運作方式與eVar類似，但是它們可以在相同點擊中包含多個值。 清單變數沒有字元限制。

請務必記錄您在解決方案設計檔案中使用每個清單變數及其邏輯 [的方式](../../prepare/solution-design.md)。

> [!NOTE] 清單變數會儲存每位訪客最近250個值。 如果指定訪客有超過250個獨特值，則最舊值不會歸因於量度。

## 在報表套裝設定中設定清單變數

請務必先在報表套裝設定中設定每個清單變數，然後再在實作中使用這些變數。 See [Conversion variables](/help/admin/admin/conversion-var-admin/list-var-admin.md) in the Admin guide.

## Adobe Experience Platform Launch中的清單變數

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## s.list1 - appMeasurement和Launch自訂代碼編輯器中的s.list3

每個清單變數都是包含您組織專屬之自訂值的字串。 它們沒有最大位元組數；但是，每個個別值最多有255個位元組。 您使用的分隔字元是在報表套裝設定中設定變數時決定。 在分隔多個項目時，請勿使用空格。

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

> [!TIP] 如果您在相同點擊中設定重複值，Adobe會消除這些值的所有例項。 例如，若您設定， `s.list1 = "Example,Example";`報表中會計入一個例項。

## 比較清單prop和清單變數

清單prop和清單變數都可以在相同點擊中包含多個值。 不過，這兩種變數類型之間有幾項主要差異。

* 任何prop都可以變成清單prop。 如果每個prop都是清單prop，則實際上最多可以有75個清單prop。 只有3個清單變數可用。
* 清單prop對整個變數有100位元組的限制。 清單變數的每個值有255位元組限制，且無總位元組限制。
* 清單prop不會持續存在超過其設定的點擊。 清單變數有任何您想要的過期設定。 不過，透過報 [告時間處理](/help/components/vrs/vrs-report-time-processing.md)，您可以將自訂歸因同時套用至清單prop和清單變數。
