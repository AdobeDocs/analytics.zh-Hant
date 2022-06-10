---
title: abort
description: abort 變數是布林值，可防止將點擊傳送至 Adobe 資料收集伺服器。
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 40%

---

# 中止

`abort` 變數是布林值，可防止將下個追蹤呼叫傳送至 Adobe。Web SDK中存在類似功能，允許您返回 `false` 發送XDM事件之前。

## 取消使用Web SDK擴展發送事件

使用 [!UICONTROL 在事件發送回調之前] 代碼編輯器和返回 `false`。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的標記屬性。
1. 轉到 [!UICONTROL 擴展] ，然後按一下 **[!UICONTROL 配置]** 按鈕 [!UICONTROL Adobe Experience PlatformWeb SDK]。
1. 下 [!UICONTROL 資料收集]，按一下 **[!UICONTROL 在事件發送回調代碼之前編輯]** 按鈕
1. 在代碼編輯器中，在任何要中止將資料發送到邊緣的條件下，放入以下代碼：

```js
return false;
```

## 取消手動發送實現Web SDK的事件

使用 `onBeforeEventSend` 回調並返回 `false`。 請參閱 [全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) 的子菜單。

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## 在Adobe Analytics擴展中使用abort變數

Adobe Analytics擴展中沒有專用欄位可使用此變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴展自定義代碼編輯器中的s.abort

`s.abort` 變數是布林值。其預設值為 `false`。

* 如果設為 `true`，下個追蹤呼叫 ([`t()`](../functions/t-method.md) 或 [`tl()`](../functions/tl-method.md)) 就不會將任何資料傳送至 Adobe。
* 若設為 `false` 或未定義，此變數就不會執行任何動作。

```js
s.abort = true;
```

>[!NOTE]
>
>`abort` 變數會在每個追蹤呼叫後重設為 `false`。如需中止相同頁面上的後續追蹤呼叫，請重新將 `abort` 設為 `true`。

例如， `abort` 可在 [`doPlugins()`](../functions/doplugins.md) 函式，該函式是在將映像請求發送到Adobe之前要運行的最後一個函式。 此示例與 `onBeforeEventSend` 使用Web SDK回調。

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

您可以集中邏輯，用於識別不想追蹤的活動，例如自訂連結或顯示廣告中的外部連結。
