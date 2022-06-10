---
title: useBeacon
description: useBeacon 可強制 AppMeasurement 使用瀏覽器 sendBeacon API
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 54%

---

# 使用信標

大部分的現代化瀏覽器都包含原生方法 `navigator.sendBeacon()`。它能以非同步方法透過 HTTP 將少量資料傳送至網頁伺服器。如果 `useBeacon` 變數已啟用，AppMeasurement 便可使用 `navigator.sendBeacon()` 方法。對於退出連結以及其他您想在頁面取消載入之前先傳送資訊的情況，此功能十分實用。

如果 `useBeacon` 已啟用，傳送至 Adobe 的下一次點擊就會使用瀏覽器的 `navigator.sendBeacon()` 方法，而非標準 `GET` 影像要求。這個變數會同時套用至 [`s.t()`](../functions/t-method.md) 和 [`s.tl()`](../functions/tl-method.md) 影像要求。它需要 AppMeasurement 2.17.0 或更新版本。

>[!TIP]
>
>AppMeasurement 會自動啟用 `useBeacon` 來處理退出連結影像要求。

當訪客使用不支援 `useBeacon` 的瀏覽器時，`navigator.sendBeacon()` 變數會遭到忽略。使用此變數需有 AppMeasurement 2.16.0 或更新版本。

## 使用Web SDK擴展使用sendBeacon API

的 **[!UICONTROL 將卸載文檔]** 「操作配置」中的複選框確定發送到Adobe的資料是否使用sendBeacon API。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的標記屬性。
1. 轉到 [!UICONTROL 規則] 頁籤，然後按一下所需的規則。
1. 下 [!UICONTROL 操作]，按一下所需的「操作」(Action)，或按一下 **&#39;+&#39;** 表徵圖以添加新操作。
1. 將「擴展」下拉清單設定為 **[!UICONTROL Adobe Experience PlatformWeb SDK]** 和 [!UICONTROL 操作類型] 至 **[!UICONTROL 發送事件]**
1. 按一下複選框 **[!UICONTROL 將卸載文檔]** 右邊。

如果選中此框，則使用sendBeacon API將資料發送到Adobe。 這項設定預設為未勾選。

## 使用sendBeacon API手動實現Web SDK

設定 `documentUnloading` 至 `true` 發送事件時。 如果未設定，則其預設值為 `false`。

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

請參閱 [使用sendBeacon API](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) 的子菜單。

## 使用信標，使用Adobe Analytics擴展

Adobe Analytics擴展中沒有專用欄位可使用此變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement中的s.useBeacon和Analytics擴展自定義代碼編輯器

`s.useBeacon` 變數是布林值，可決定 AppMeasurement 是否要使用瀏覽器的 `navigator.sendBeacon()` 方法。其預設值為 `false`。如果您要使用 `navigator.sendBeacon()` 的非同步性，請在呼叫追蹤函數之前將此變數設為 `true`。

```js
s.useBeacon = true;
```

>[!NOTE]
>
>在執行追蹤呼叫後，此變數會重設為 `false`。 如果您的實作在相同頁面載入中傳送多個影像要求 (像是單頁應用程式)，請在每次追蹤呼叫前將此變數設定為 `true`。
