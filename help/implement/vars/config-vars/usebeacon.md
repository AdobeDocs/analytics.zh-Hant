---
title: useBeacon
description: useBeacon 可強制 AppMeasurement 使用瀏覽器 sendBeacon API
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 61%

---

# useBeacon

大部分的現代化瀏覽器都包含原生方法 `navigator.sendBeacon()`。它能以非同步方法透過 HTTP 將少量資料傳送至網頁伺服器。如果 `useBeacon` 變數已啟用，AppMeasurement 便可使用 `navigator.sendBeacon()` 方法。對於退出連結以及其他您想在頁面取消載入之前先傳送資訊的情況，此功能十分實用。

如果 `useBeacon` 已啟用，傳送至 Adobe 的下一次點擊就會使用瀏覽器的 `navigator.sendBeacon()` 方法，而非標準 `GET` 影像要求。這個變數會同時套用至 [`s.t()`](../functions/t-method.md) 和 [`s.tl()`](../functions/tl-method.md) 影像要求。它需要 AppMeasurement 2.17.0 或更新版本。

>[!TIP]
>
>AppMeasurement 會自動啟用 `useBeacon` 來處理退出連結影像要求。

當訪客使用不支援 `useBeacon` 的瀏覽器時，`navigator.sendBeacon()` 變數會遭到忽略。使用此變數需有 AppMeasurement 2.16.0 或更新版本。

## 使用Web SDK擴充功能的sendBeacon API

此 **[!UICONTROL 文檔將卸載]** 「動作設定」中的核取方塊會決定傳送至「Adobe」的資料是否使用sendBeacon API。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往 [!UICONTROL 規則] 標籤，然後按一下所需的規則。
1. 在 [!UICONTROL 動作]，按一下所需的動作，或按一下 **&#39;+&#39;** 圖示以新增動作。
1. 將「擴充功能」下拉式清單設為 **[!UICONTROL Adobe Experience Platform Web SDK]** 和 [!UICONTROL 動作類型] to **[!UICONTROL 傳送事件]**
1. 按一下核取方塊 **[!UICONTROL 文檔將卸載]** 在右邊。

如果核取此方塊，則會使用sendBeacon API將資料傳送至Adobe。 這項設定預設為未勾選。

## 使用sendBeacon API手動實作Web SDK

設定 `documentUnloading` to `true` 傳送事件時。 若未設定，其預設值為 `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

請參閱 [使用sendBeacon API](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) 如需詳細資訊，請參閱網頁SDK檔案。

## 使用Adobe Analytics擴充功能使用信標

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.useBeacon

`s.useBeacon` 變數是布林值，可決定 AppMeasurement 是否要使用瀏覽器的 `navigator.sendBeacon()` 方法。其預設值為 `false`。如果您要使用 `navigator.sendBeacon()` 的非同步性，請在呼叫追蹤函數之前將此變數設為 `true`。

```js
s.useBeacon = true;
```

>[!NOTE]
>
>在執行追蹤呼叫後，此變數會重設為 `false`。 如果您的實作在相同頁面載入中傳送多個影像要求 (像是單頁應用程式)，請在每次追蹤呼叫前將此變數設定為 `true`。
