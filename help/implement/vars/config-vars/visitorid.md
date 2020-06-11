---
title: visitorID
description: 使用自訂訪客 ID。
translation-type: tm+mt
source-git-commit: b9bb7a60398b8c392393a8d16b58292f91ab0ea7
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 71%

---


# visitorID

Adobe 使用數種不同的方法來識別您網站上的訪客。`visitorID` 變數會覆寫其他所有訪客識別方法。

>[!IMPORTANT] Adobe 建議您不要使用此變數。請改用 [Adobe Experience Cloud Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.html)。

## Adobe Experience Platform Launch 中的訪客 ID

[!UICONTROL 「訪客 ID」]是在設定 Adobe Analytics 擴充功能時，於[!UICONTROL 「Cookie」]設定追蹤器下方的欄位。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「Cookie」]設定追蹤器，如此可顯示[!UICONTROL 「訪客 ID」]欄位。

將此欄位指派給包含自訂訪客 ID 的資料元素。請勿將此欄位設為靜態值。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.visitorID

`s.visitorID` 變數是包含訪客自訂唯一識別碼的字串。有效值包括最多 100 個位元組的英數字元。請避免在此變數中使用虛線、空格、底線或符號。

>[!WARNING] 如果您在瀏覽途中 `visitorID` 設定變數，資料會產生兩個不同的不重複訪客。

```js
s.visitorID = "abc123";
```

>[!CAUTION] 自訂訪客ID的無效實作可能導致資料不正確，並造成報告效能不佳。 如果此變數包含預設值( `"0"` 如 `"NULL"`或),Adobe會將這些點擊視為相同的訪客。 此情況會導致資料不正確，訪客數量較少，而訪客層級區段無法如預期般運作。 錯誤實作的自訂訪客ID也會在處理伺服器上造成大量負載，增加延 [遲](/help/technotes/latency.md) ，並降低報表效能。
