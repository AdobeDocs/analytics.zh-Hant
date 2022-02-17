---
title: 伺服器
description: 填入「伺服器」維度。
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 100%

---

# 伺服器

`server` 變數通常會儲存網站的主機名稱。它常用於包含多個網域資料的報表套裝。它的功能與 prop 相同。

## 使用 Adobe Experience Platform 中的標記的伺服器

您可以在設定 Analytics 擴充功能 (全域變數) 時或是在規則底下設定伺服器。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標記，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「伺服器」]區段。

您可以將伺服器設定為任何字串值或資料元素。

## AppMeasurement 和自訂程式碼編輯器中的 s.server

`s.server` 變數是字串，通常包含網站的主機名稱。其最大值為 100 個位元組；超過上限的值會遭到截斷。

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
