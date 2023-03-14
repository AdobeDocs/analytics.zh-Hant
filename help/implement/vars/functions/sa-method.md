---
title: sa
description: 隨時在您的實施中變更報表套裝。
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 44%

---

# sa

`sa()` 方法可讓您隨時在頁面上動態變更報表套裝。如果您想要在不重新載入頁面的情況下，將資料傳送至不同的報表套裝，可以使用此方法。

## 使用Web SDK處理報表套裝

Web SDK的運作方式是傳送資料至特定的資料流，該資料流會將資料轉送至所需的Analytics報表套裝。 單一資料流可將資料轉送至多個報表套裝。 本節適用於Web SDK擴充功能和手動實作Web SDK。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下 **[!UICONTROL 資料流]** 左邊。
1. 按一下所需的資料流，或按一下 **[!UICONTROL 新資料流]**.
1. 按一下 **[!UICONTROL 添加服務]**，然後選取 **[!UICONTROL Adobe Analytics]**.
1. 輸入所需的報表套裝ID。 如果您想要將相同的資料傳送至多個報表套裝，請按一下 **[!UICONTROL 新增報表套裝]**.
1. 輸入所有需要的報表套裝後，按一下 **[!UICONTROL 儲存]**.

## 使用Web SDK擴充功能設定所需的資料流

Web SDK擴充功能提供適用於每個環境的資料流下拉式清單。 或者，您也可以手動輸入資料流ID。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往 [!UICONTROL 擴充功能] ，然後按一下 **[!UICONTROL 設定]** 按鈕 [!UICONTROL Adobe Experience Platform Web SDK].
1. 在 [!UICONTROL 資料流]，請在下拉式清單中針對每個環境選擇所需的資料流。
1. 按一下「**[!UICONTROL 儲存]**」。

## 手動設定實作Web SDK所需的資料流

設定 `edgeConfigId` 設定變數至資料流ID。 在Adobe Experience Platform資料收集中檢視資料流時，可在右側找到資料流ID。

```js
alloy("configure", {
  "edgeConfigId": "example-a01f-4458-8cec-ef61de241c93",
});
```

請參閱 [配置Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant) 如需詳細資訊，請參閱網頁SDK檔案。

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
