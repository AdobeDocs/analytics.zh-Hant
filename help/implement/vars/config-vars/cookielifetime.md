---
title: cookieLifetime
description: 覆寫 AppMeasurement 所建立 Cookie 的有效期。
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 90%

---

# cookieLifetime

AppMeasurement 所設定的 Cookie 通常有效期為 2 年。可使用 `cookieLifetime` 變數覆寫 AppMeasurement 所設定 Cookie 的到期日。

>[!NOTE]
>
>此變數會影響不重複訪客計數和歸因。設定此變數時請小心。

## 在Adobe Experience Platform中使用標籤的Cookie期限

「Cookie 期限」是設定 Adobe Analytics 擴充功能時[!UICONTROL 一般]摺疊式功能表底下的下拉式清單。

1. 使用您的AdobeID憑證登入[資料收集UI](https://experience.adobe.com/data-collection)。
1. 按一下所需的屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
1. 展開 [!UICONTROL Cookies] 摺疊式功能表，便會顯示 [!UICONTROL Cookie 期限]下拉式清單。

此下拉式清單包含下列值：

* **預設值**：Cookie 會在 2 年後到期。
* **無**：AppMeasurement 不設定 Cookie。
* **作業階段**：Cookie 會在訪客的作業階段結束時到期。
* **秒**：Cookie 會在指定的秒數過後到期。例如，將此下拉式清單設定為[!UICONTROL 秒]，並將 `86400` 放入自訂欄位中，便會強制 Cookie 在 24 小時後到期。

## AppMeasurement 和 自訂程式碼編輯器中的 s.cookieLifetime

`s.cookieLifetime` 變數為字串，可決定 AppMeasurement 所設定 Cookie 的到期日。

* 如果設為 `SESSION`，AppMeasurement 設定的 Cookie 會在瀏覽器作業階段完成後到期。
* 如果設為 `NONE`，AppMeasurement 不會嘗試設定 Cookie。
* 如果設為整數字串，AppMeasurement 所設定的 Cookie 會在指定秒數過後到期。

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
