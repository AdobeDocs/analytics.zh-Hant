---
title: eVar
description: 您可在實作中使用的自訂變數。
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# eVar

eVar是自訂變數，您可以視需要使用。

> [!TIP] Adobe建議在大部分情況下使用eVar來取代prop。 在舊版Adobe Analytics中，prop和eVar有其優缺點。 不過，Adobe已將eVar改良為幾乎可完成所有prop使用案例的eVar。

請務必記錄您在解決方案設計檔案中使用每個eVar及其邏 [輯的方式](../../prepare/solution-design.md)。

## 在報表套裝設定中設定eVar

在實作中使用eVar之前，請務必在報表套裝設定中設定每個eVar。 See [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

## Adobe Experience Platform Launch中的eVar

您可以在設定Analytics擴充功能（全域變數）時或在規則下設定eVar。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下方，按一下現有  的Adobe Analytics - 「設定變數」動作，或按一下「+」圖示。
5. 將「延伸 [!UICONTROL 功能] 」下拉式清單設定為Adobe Analytics，並將「動作類型 [!UICONTROL 」設] 定為變數 。
6. 找到 [!UICONTROL eVars區段] 。

您可以選取eVar來設定值或資料元素。 您也可以從其他Analytics變數複製值。

## s.eVar1 - appMeasurement和Launch自訂代碼編輯器中的s.eVar250

每個eVar都是包含您組織專屬之自訂值的字串。 最大長度為255個位元組；超過255個位元組的值會在傳送至Adobe時自動截斷。

```js
s.eVar1 = "Example custom value";
```

## 計數器 eVar

eVar值通常包含字串值。 不過，您可以設定eVar，改為包含計數器。 例如，您想要計算購買前進行的內部搜尋數目。 您應使用下列語法，而非設定文字值：

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

若指定了兩個以上的小數位數，eVar 計數器會進位至兩個小數位數。eVar計數器不能包含負數。

## prop或eVar的獨享優勢

在目前的Adobe Analytics版本中，prop和eVar都是具有類似功能的自訂變數。 但是，它們有幾大不同：

* Prop中的資料可在數分鐘內供報告使用。 eVar可能需要超過30分鐘才會顯示在報表中。
* Prop的報表限制為100位元組。 eVar有255位元組的限制。
* Prop可成為清單Prop，這些Prop在同一點擊中接受多個值。 清單變數是個別的變數，只有三個清單變數可供使用。
* Prop預設不會持續存在超過設定的點擊。 eVar有自訂的過期時間，可讓您判斷eVar何時不再獲得後續事件的評分。 如果您使 [用報表時間處理](../../../components/vrs/vrs-report-time-processing.md),prop和eVar都可以使用任何您想要的歸因模型。
