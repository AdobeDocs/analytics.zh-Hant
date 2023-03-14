---
title: abort
description: abort 變數是布林值，可防止將點擊傳送至 Adobe 資料收集伺服器。
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 48%

---

# abort

`abort` 變數是布林值，可防止將下個追蹤呼叫傳送至 Adobe。Web SDK中也有類似的功能，可讓您傳回 `false` XDM事件傳送之前。

## 使用Web SDK擴充功能取消傳送事件

使用 [!UICONTROL 在事件傳送回呼之前] 程式碼編輯器與傳回 `false`.

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往 [!UICONTROL 擴充功能] ，然後按一下 **[!UICONTROL 設定]** 按鈕 [!UICONTROL Adobe Experience Platform Web SDK].
1. 在 [!UICONTROL 資料收集]，按一下 **[!UICONTROL 在事件傳送回呼程式碼之前編輯]** 按鈕。
1. 在程式碼編輯器中，針對您要中止將資料傳送至Edge的任何條件，放入下列程式碼：

```js
return false;
```

## 取消傳送手動實作Web SDK的事件

使用 `onBeforeEventSend` 回撥及傳回 `false`. 請參閱 [全域修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) 如需詳細資訊，請參閱網頁SDK檔案。

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## 在Adobe Analytics擴充功能中使用abort變數

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.abort

`s.abort` 變數是布林值。其預設值為 `false`。

* 如果設為 `true`，下個追蹤呼叫 ([`t()`](../functions/t-method.md) 或 [`tl()`](../functions/tl-method.md)) 就不會將任何資料傳送至 Adobe。
* 若設為 `false` 或未定義，此變數就不會執行任何動作。

```js
s.abort = true;
```

>[!NOTE]
>
>`abort` 變數會在每個追蹤呼叫後重設為 `false`。如需中止相同頁面上的後續追蹤呼叫，請重新將 `abort` 設為 `true`。

例如， `abort` 變數可在 [`doPlugins()`](../functions/doplugins.md) 函式，此函式是在將影像要求傳送至Adobe之前，要執行的最後一個函式。 此範例的運作方式與 `onBeforeEventSend` 使用Web SDK進行回呼。

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

您可以集中邏輯，用於識別不想追蹤的活動，例如自訂連結或顯示廣告中的外部連結。
