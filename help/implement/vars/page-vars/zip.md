---
title: zip
description: 如果報表套裝設定允許，手動填入「郵遞區號」維度。
feature: Appmeasurement Implementation
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 75%

---

# zip

如果報表套裝設定中的[!UICONTROL 「郵政編碼選項」]允許，`zip` 變數可讓您手動填入「郵遞區號」維度。在舊版 Adobe Analytics 中，此變數只能手動設定，通常是在零售網站上輸入運送資訊時。Adobe Analytics 的改良功能讓您可以使用地理位置資料自動設定此變數。此變數不會持續存在超過其設定的點擊。

>[!IMPORTANT]
>
> 請確認報表套裝設定中的[!UICONTROL 「郵政編碼選項」]已設為所要的值。如果您一律使用[!UICONTROL 地理zip]，便無法使用此變數。 如需詳細資訊，請參閱「管理員使用指南」中的[一般帳戶設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)。

## 使用網頁SDK的郵遞區號

郵遞區號會對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.placeContext.geo.postalCode`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.zip`

## 使用Adobe Analytics擴充功能的郵遞區號

您可以在設定Analytics擴充功能（全域變數）時設定郵遞區號，或依據規則進行設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 擴充功能]下拉式清單設定為Adobe Analytics，並將[!UICONTROL 動作型別]設定為[!UICONTROL 設定變數]。
6. 找出[!UICONTROL 「Zip」]區段。

您可以將郵遞區號設為任何字串值，包括資料元素。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.zip

`s.zip` 變數是一個字串，通常包含郵遞區號，不過可以包含任何需要的值，長度最多 50 個位元組。

```js
s.zip = "84043";
```
