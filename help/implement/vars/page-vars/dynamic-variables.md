---
title: 動態變數
description: 複製變數而不增加影像要求長度。
feature: Variables
exl-id: 41aab44d-01fd-45fe-892d-637d69488d98
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 77%

---

# 動態變數

動態變數可讓您將值從某個變數複製到另一個變數，而不增加影像要求的長度。在多個變數中擷取相同資料時，這些變數很有幫助。

在舊版 Analytics 中，影像要求長度是預防資料截斷非常重要的環節。AppMeasurement 改良功能容許的影像要求查詢字串長度大幅增加，因此通常不需要動態變數。

動態變數支援在影像要求中使用查詢字串參數或 HTTP 標題。如需可參考的可用參數完整清單，請參閱[資料彙集查詢參數](../../validate/query-parameters.md)。如需可參考的可用 HTTP 要求欄位完整清單，請參閱 Wikipedia 上的[標準要求欄位](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields)。

當 Adobe 辨識出動態變數首碼時，會自動複製報表套裝中的查詢字串或 HTTP 標題值。此動作會在其他任何處理 (包括處理規則和 VISTA 規則) 之前進行。

>[!TIP]
>
>複製變數時請留意字元上限。例如，如果將 `eVar1` 複製到 `prop1`，`prop1` 的值可能會遭到截斷，因為它有 100 個位元組的限制 (`eVar1` 則有 255 個位元組的限制)。

## 使用Web SDK的動態變數

使用資料流映射將資料從單個XDM欄位發送到多個分析變數。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下 **[!UICONTROL 資料流]** 左欄。
1. 按一下所需的資料流。
1. 按一下 **[!UICONTROL 編輯映射]** 右邊。
1. 映射所需 [!UICONTROL 源欄位] 到期望的 [!UICONTROL 目標欄位]。 單個源欄位可以映射到任意數量的目標欄位。

## 使用Adobe Analytics擴展的動態變數

您可以在任何接受字串的維度欄位中使用動態變數。 維度項目通常會在設定 Analytics 擴充功能 (全域變數) 時設定，或依據規則進行設定。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
2. 按一下所需的標記屬性。
3. 前往[!UICONTROL 規則]標記，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出所需的維度項目。

將動態變數首碼放置在文字欄位中，隨後加上您要參考的查詢字串參數或 HTTP 標題。依預設，動態變數首碼為 `D=`。

## AppMeasurement和Analytics擴展自定義代碼編輯器中的動態變數

動態變數是指派給其他變數的文字字串。預設的動態變數首碼為 `D=`。動態變數會區分大小寫。

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

>[!NOTE]
>
> 在為實施作業除錯時，動態變數會顯示為字串。值由 Adobe 資料收集伺服器從伺服器端複製。
