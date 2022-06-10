---
title: sa
description: 隨時在您的實施中變更報表套裝。
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 38%

---

# 沙

`sa()` 方法可讓您隨時在頁面上動態變更報表套裝。如果您想要在不重新載入頁面的情況下，將資料傳送至不同的報表套裝，可以使用此方法。

## 使用Web SDK處理報表套件

Web SDK通過向特定資料流發送資料來操作，該資料流將資料轉發到所需的分析報告套件。 單個資料流可以將資料轉發到多個報表套件。 本節適用於Web SDK擴展和手動實現Web SDK。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下 **[!UICONTROL 資料流]** 左邊。
1. 按一下所需的資料流，或按一下 **[!UICONTROL 新建資料流]**。
1. 按一下 **[!UICONTROL 添加服務]**，然後選擇 **[!UICONTROL Adobe Analytics]**。
1. 輸入所需的報表套件ID。 如果要將相同的資料發送到多個報表套件，請按一下 **[!UICONTROL 添加報表套件]**。
1. 輸入所有所需的報告套件後，按一下 **[!UICONTROL 保存]**。

## 使用Web SDK擴展設定所需的資料流

Web SDK擴展為每個環境提供一個資料流下拉清單。 或者，可以手動輸入資料流ID。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的標記屬性。
1. 轉到 [!UICONTROL 擴展] ，然後按一下 **[!UICONTROL 配置]** 按鈕 [!UICONTROL Adobe Experience PlatformWeb SDK]。
1. 下 [!UICONTROL 資料流]，在下拉菜單中為每個環境選擇所需的資料流。
1. 按一下&#x200B;**[!UICONTROL 儲存]**。

## 手動設定所需的資料流以實現Web SDK

設定 `edgeConfigId` 資料流ID的配置變數。 在Adobe Experience Platform資料集中查看資料流時，在右側找到資料流ID。

```js
alloy("configure", {
  "edgeConfigId": "example-a01f-4458-8cec-ef61de241c93",
});
```

請參閱 [配置Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant) 的子菜單。

## 使用Adobe Analytics擴展更改報告套件

在介面中變更報表套裝沒有彈性的方式。設定 Adobe Analytics 擴充功能時，您可以在[!UICONTROL 「資料庫管理」]摺疊式功能表下方設定報表套裝。不過，您無法使用規則變更或更新報表套裝。如果您想要在設定報表套裝值後更新這些值，請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## s.sa()（在AppMeasurement中）和Analytics擴展自定義代碼編輯器中)

呼叫 `s.sa()` 方法變更目的地報表套裝。其唯一引數是包含報表套裝 ID 的字串，或是多個以逗號分隔的報表套裝 ID。報表套裝 ID 引數為必要項目。請勿在字串引數中使用空格。

```js
s.sa("examplersid");
```

例如，如果用戶在您的站點上執行特定操作，則可以更改報告套件。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
