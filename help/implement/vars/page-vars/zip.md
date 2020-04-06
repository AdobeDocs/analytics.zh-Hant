---
title: zip
description: 如果報表套裝設定允許，手動填入「郵遞區號」維度。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# zip

The `zip` variable allows you to manually populate the &#39;Zip Code&#39; dimension if the [!UICONTROL Zip Option] in report suite settings allows it. 在舊版 Adobe Analytics 中，此變數只能手動設定，通常是在零售網站上輸入運送資訊時。Adobe Analytics 的改良功能讓您可以使用地理位置資料自動設定此變數。此變數不會持續存在超過其設定的點擊。

>[!IMPORTANT] 請確定報 [!UICONTROL Zip Option] 表套裝中的設定已設定為所需值。 如果您一律使用[!UICONTROL geo zip]「」，便無法使用此變數。如需詳細資訊，請參閱「管理員使用指南」中的[一般帳戶設定](/help/admin/admin/general-acct-settings-admin.md)。

## Adobe Experience Platform Launch 中的 Zip

您可以在設定 Analytics 擴充功能 (全域變數) 時設定郵遞區號，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. 在下 [!UICONTROL Actions]方，按一下現 [!UICONTROL Adobe Analytics - Set Variables] 有動作或按一下「+」圖示。
5. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為 [!UICONTROL Set Variables]。
6. Locate the [!UICONTROL Zip] section.

您可以將郵遞區號設為任何字串值，包括資料元素。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.zip

`s.zip` 變數是一個字串，通常包含郵遞區號，不過可以包含任何需要的值，長度最多 50 個位元組。

```js
s.zip = "84043";
```
