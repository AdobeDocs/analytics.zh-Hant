---
title: cookieLifetime
description: 覆寫 AppMeasurement 所建立 Cookie 的有效期。
feature: Variables
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 64%

---

# cookieLifetime

AppMeasurement 所設定的 Cookie 通常有效期為 2 年。可使用 `cookieLifetime` 變數覆寫 AppMeasurement 所設定 Cookie 的到期日。

>[!NOTE]
>
>此變數會影響不重複訪客計數和歸因。設定此變數時請小心。

## 使用Web SDK的Cookie期限

Web SDK尚未針對其設定的Cookie存留期提供自訂。

## 使用Adobe Analytics擴充功能的Cookie期限

Cookie期限是 [!UICONTROL Cookie] 設定Adobe Analytics擴充功能時設定折疊式功能表。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開 [!UICONTROL Cookie] 折疊式功能表，可顯示 [!UICONTROL Cookie期限] 下拉式清單。

此下拉式清單包含下列值：

* **預設值**：Cookie 會在 2 年後到期。
* **無**：AppMeasurement 不設定 Cookie。
* **作業階段**：Cookie 會在訪客的作業階段結束時到期。
* **秒**：Cookie 會在指定的秒數過後到期。例如，將此下拉式清單設為 [!UICONTROL 秒] 放置 `86400` 在自訂欄位中，會強制cookie在24小時後過期。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.cookieLifetime

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
