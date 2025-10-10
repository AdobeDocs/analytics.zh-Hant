---
title: visitorID
description: 使用自訂訪客 ID。
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 71%

---

# visitorID

Adobe 使用數種不同的方法來識別您網站上的訪客。`visitorID` 變數會覆寫其他所有訪客識別方法。

>[!IMPORTANT]
>
>Adobe 建議您不要使用此變數。請改用 [Adobe Experience Cloud 身分識別服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)。

## 使用Adobe Analytics擴充功能的訪客ID

「[!UICONTROL 訪客 ID]」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL Cookie]」摺疊式功能表下方的欄位。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「Cookie」]摺疊式功能表，如此可顯示[!UICONTROL 「訪客 ID」]欄位。

將此欄位指派給包含自訂訪客 ID 的資料元素。請勿將此欄位設為靜態值。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.visitorID

`s.visitorID` 變數是包含訪客自訂唯一識別碼的字串。有效值包括最多 100 個位元組的英數字元。請避免在此變數中使用虛線、空格、底線或符號。

>[!WARNING]
>
>如果您在瀏覽途中 `visitorID` 設定變數，資料會產生兩個不同的不重複訪客。

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>自訂訪客 ID 的無效實施作業可能導致資料不正確，並造成報告效能不佳。如果此變數包含預設值 (例如 `"0"` 或 `"NULL"`)，則 Adobe 會將這些點擊視為相同的訪客。此情況會導致資料不正確、訪客計數偏低，以及訪客層級區段的運作不如預期。不當實施作業的自訂訪客 ID 也會對處理伺服器造成大量負載、增加[延遲](/help/technotes/latency.md)，並降低報表效能。

## 使用網頁SDK的訪客ID

Adobe Experience Platform Edge Network可讓您使用XDM的[身分對應](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html#using-identitymap)來提供多個識別碼。 「身分對應」中的每個身分都有不同的名稱空間。 您可以在[資料流設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#analytics)中，指定訪客ID應該使用哪個名稱空間。 完成設定後，當您傳送具有為此名稱空間指定值的事件時，系統會自動將其用作Analytics中的訪客ID。
