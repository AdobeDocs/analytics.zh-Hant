---
title: cookieLifetime
description: 覆寫AppMeasurement所建立之Cookie的有效期。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# cookieLifetime

由AppMeasurement設定的Cookie通常有2年的有效期。 使用變 `cookieLifetime` 數來覆寫AppMeasurement所設定Cookie的到期日。

> [!NOTE] 此變數會影響獨特訪客計數和歸因。 設定此變數時請小心。

## Adobe Experience Platform Launch中的Cookie期限

Cookie存留期是設定Adobe Analytics擴充功 [!UICONTROL 能時Cookie] accordion下方的下拉式清單。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開 [!UICONTROL Cookies accordion] ，此下拉式清單會顯 [!UICONTROL 示Cookie存留期] 。

此下拉式清單包含下列值：

* **預設值**:Cookie會在2年後到期。
* **無**:AppMeasurement不會設定Cookie。
* **會話**:Cookie會在訪客作業結束時過期。
* **秒**:Cookie會在指定的秒數過後過期。 例如，將此下拉式清單設 [!UICONTROL 定為] 「秒」，並 `86400` 將它放入自訂欄位，會強制Cookie在24小時後過期。

## AppMeasurement和Launch自訂代碼編輯器中的s.cookieLifetime

變 `s.cookieLifetime` 數是一個字串，可決定AppMeasurement所設定Cookie的到期日。

* 如果設為 `SESSION`,AppMeasurement設定的Cookie會在瀏覽器作業完成後過期。
* 如果設 `NONE`定為，AppMeasurement不會嘗試設定Cookie。
* 如果設為整數字串，AppMeasurement設定的Cookie會在指定秒數過後過期。

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";

