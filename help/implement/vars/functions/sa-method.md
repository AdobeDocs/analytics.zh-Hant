---
title: sa
description: 隨時在您的實施中變更報表套裝。
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 42%

---

# sa

`sa()` 方法可讓您隨時在頁面上動態變更報表套裝。如果您想要在不重新載入頁面的情況下，將資料傳送至不同的報表套裝，可以使用此方法。

## 使用Web SDK處理報表套裝

Web SDK的運作方式是將資料傳送至特定資料流，該資料流會將資料轉送至所需的Analytics報表套裝。 單一資料流可轉送資料至多個報表套裝。 本節同時適用於Web SDK擴充功能和手動實作Web SDK。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下 **[!UICONTROL 資料串流]** 左側。
1. 按一下所需的資料流，或按一下 **[!UICONTROL 新增資料串流]**.
1. 按一下 **[!UICONTROL 新增服務]**，然後選取 **[!UICONTROL Adobe Analytics]**.
1. 輸入所需的報表套裝ID。 如果您想要將相同的資料傳送至多個報表套裝，請按一下 **[!UICONTROL 新增報表套裝]**.
1. 輸入所有需要的報表套裝後，按一下 **[!UICONTROL 儲存]**.

## 使用Web SDK擴充功能設定所需的資料串流

Web SDK擴充功能提供每個環境的資料串流下拉式清單。 或者，您可以手動輸入資料串流ID。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往 [!UICONTROL 擴充功能] 標籤，然後按一下 **[!UICONTROL 設定]** 按鈕在 [!UICONTROL Adobe Experience Platform Web SDK].
1. 在 [!UICONTROL 資料串流]，從每個環境的下拉式清單中選擇所需的資料串流。
1. 按一下「**[!UICONTROL 儲存]**」。

## 手動設定所需資料流以實作Web SDK

設定 `edgeConfigId` 設定變數重新命名為Datastream ID。 在Adobe Experience Platform Data Collection中檢視資料流時，可在右側找到資料流ID。

```js
alloy("configure", {
  "edgeConfigId": "example-a01f-4458-8cec-ef61de241c93",
});
```

另請參閱 [設定Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant) 詳細資訊，請參閱Web SDK檔案。

## 使用Adobe Analytics擴充功能變更報表套裝

在介面中變更報表套裝沒有彈性的方式。設定 Adobe Analytics 擴充功能時，您可以在[!UICONTROL 「資料庫管理」]摺疊式功能表下方設定報表套裝。不過，您無法使用規則變更或更新報表套裝。如果您想要在設定報表套裝值後更新這些值，請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.sa()

呼叫 `s.sa()` 方法變更目的地報表套裝。其唯一引數是包含報表套裝 ID 的字串，或是多個以逗號分隔的報表套裝 ID。報表套裝 ID 引數為必要項目。請勿在字串引數中使用空格。

```js
s.sa("examplersid");
```

例如，如果使用者在您的網站上採取特定動作，您可以變更報表套裝。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
