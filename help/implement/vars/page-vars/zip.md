---
title: zip
description: 如果報表套裝設定允許，請手動填入「郵遞區號」維度。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# zip

如果 `zip` 報表套裝設定中的「郵遞區號選項」允許，此變數可讓您手動填入「 [!UICONTROL 郵遞區號] 」維度。 在舊版Adobe Analytics中，此變數只能手動設定，通常是在零售網站上輸入運送資訊時。 Adobe Analytics的改進功能可讓此變數使用地理位置資料自動設定。 此變數不會持續存在超過其設定的點擊範圍。

> [!IMPORTANT] 請確定報 [!UICONTROL 表套裝設定中的] 「郵遞區號選項」已設定為所要的值。 如果始終使用地理郵 [!UICONTROL 遞區號] ，則無法使用此變數。 See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

## Adobe Experience Platform Launch中的Zip

您可以在設定Analytics擴充功能（全域變數）時或在規則下設定郵遞區號。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下方，按一下現有  的Adobe Analytics - 「設定變數」動作，或按一下「+」圖示。
5. 將「延伸 [!UICONTROL 功能] 」下拉式清單設定為Adobe Analytics，並將「動作類型 [!UICONTROL 」設] 定為變數 。
6. 找到 [!UICONTROL Zip] 區段。

您可以將郵遞區號設為任何字串值，包括資料元素。

## AppMeasurement和Launch自訂代碼編輯器中的s.zip

變 `s.zip` 數是一個字串，通常包含郵遞區號，但可包含任何需要的值，長度最多50位元組。

```js
s.zip = "84043";
```
