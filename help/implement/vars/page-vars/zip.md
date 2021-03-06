---
title: zip
description: 如果報表套裝設定允許，手動填入「郵遞區號」維度。
feature: Variables
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 88%

---

# 郵遞區號

如果報表套裝設定中的[!UICONTROL 「郵政編碼選項」]允許，`zip` 變數可讓您手動填入「郵遞區號」維度。在舊版 Adobe Analytics 中，此變數只能手動設定，通常是在零售網站上輸入運送資訊時。Adobe Analytics 的改良功能讓您可以使用地理位置資料自動設定此變數。此變數不會持續存在超過其設定的點擊。

>[!IMPORTANT]
>
> 請確認報表套裝設定中的[!UICONTROL 「郵政編碼選項」]已設為所要的值。如果您一律使用[!UICONTROL 「geo zip」]，便無法使用此變數。如需詳細資訊，請參閱「管理員使用指南」中的[一般帳戶設定](/help/admin/admin/general-acct-settings-admin.md)。

## 使用Adobe Analytics分機

您可以在設定 Analytics 擴充功能 (全域變數) 時設定郵遞區號，或依據規則進行設定。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
2. 按一下所需的標記屬性。
3. 前往[!UICONTROL 規則]標記，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「Zip」]區段。

您可以將郵遞區號設為任何字串值，包括資料元素。

## AppMeasurement中的s.zip和分析擴展自定義代碼編輯器

`s.zip` 變數是一個字串，通常包含郵遞區號，不過可以包含任何需要的值，長度最多 50 個位元組。

```js
s.zip = "84043";
```
