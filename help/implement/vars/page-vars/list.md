---
title: list
description: 在同一次點擊中容納多個值的自訂變數。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# list

清單變數是自訂變數，您可以視需要使用。它們的作用與 eVar 類似，但是它們可以在同一次點擊中包含多個值。清單變數沒有字元限制。

請務必將每個清單變數的使用方式與其邏輯記錄在[解決方案設計文件](../../prepare/solution-design.md)內。

>[!NOTE] 清單變數能儲存每位訪客最近 250 個值。如果特定訪客擁有超過 250 個獨特值，則最舊的值不會歸入量度。

## 在報表套裝設定中設定清單變數

在實施中使用清單變數之前，請務必先在報表套裝設定中設定每個變數。請參閱「管理員指南」中的[轉換變數](/help/admin/admin/conversion-var-admin/list-var-admin.md)。

## Adobe Experience Platform Launch 中的清單變數

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.list1 - s.list3

每個清單變數都是字串，其中包含貴組織專屬的自訂值。它們沒有位元組數上限，不過每個個別的值有最多 255 個位元組的上限。您使用的分隔字元，可以在報表套裝設定中設定變數時決定。在分隔多個項目時，請勿使用空格。

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP] 如果您在同一次點擊中設定重複值，Adobe 會去除這些值的所有例項。例如，若您設定 `s.list1 = "Example,Example";`，報表只會計入一個例項。

## 比較清單屬性和清單變數

清單屬性和清單變數都可以在同一次點擊中包含多個值。不過，這兩種變數類型之間有幾項主要差異。

* 任何屬性都可以變成清單屬性。如果每個屬性都是清單屬性，實際上您最多可以擁有 75 個清單屬性。可用的清單變數只有 3個。
* 清單屬性的整個變數有 100 個位元組的限制。清單變數的每個值有 255 個位元組的限制，但是沒有位元組總數限制。
* 清單屬性不會持續存在超過其設定的點擊。清單變數的過期設定可以是您想要的任何設定。不過，透過[報表時間處理](/help/components/vrs/vrs-report-time-processing.md)，您可以將自訂歸因同時套用至清單屬性和清單變數。
