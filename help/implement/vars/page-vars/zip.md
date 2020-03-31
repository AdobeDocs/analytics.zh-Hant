---
title: zip
description: 如果報表套裝設定允許，手動填入「郵遞區號」維度。
translation-type: ht
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# zip

如果報表套裝設定中的[!UICONTROL 「郵政編碼選項」]允許，`zip` 變數可讓您手動填入「郵遞區號」維度。在舊版 Adobe Analytics 中，此變數只能手動設定，通常是在零售網站上輸入運送資訊時。Adobe Analytics 的改良功能讓您可以使用地理位置資料自動設定此變數。此變數不會持續存在超過其設定的點擊。

> [!IMPORTANT] 請確認報表套裝設定中的[!UICONTROL 「郵政編碼選項」]已設定為所要的值。如果您一律使用[!UICONTROL 「geo zip」]，便無法使用此變數。如需詳細資訊，請參閱「管理員使用指南」中的[一般帳戶設定](/help/admin/admin/general-acct-settings-admin.md)。

## Adobe Experience Platform Launch 中的 Zip

您可以在設定 Analytics 擴充功能 (全域變數) 時設定郵遞區號，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「Zip」]區段。

您可以將郵遞區號設為任何字串值，包括資料元素。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.zip

`s.zip` 變數是一個字串，通常包含郵遞區號，不過可以包含任何需要的值，長度最多 50 個位元組。

```js
s.zip = "84043";
```
