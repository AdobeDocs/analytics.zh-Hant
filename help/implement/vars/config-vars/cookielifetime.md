---
title: cookieLifetime
description: 覆寫 AppMeasurement 所建立 Cookie 的有效期。
feature: Variables
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 80%

---

# cookie生存期

AppMeasurement 所設定的 Cookie 通常有效期為 2 年。可使用 `cookieLifetime` 變數覆寫 AppMeasurement 所設定 Cookie 的到期日。

>[!NOTE]
>
>此變數會影響不重複訪客計數和歸因。設定此變數時請小心。

## 使用Web SDK的Cookie生存期

Web SDK尚未為其設定的Cookie的生命週期提供自定義。

## 使用Adobe Analytics擴展的Cookie生存期

「Cookie 期限」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL Cookie]」摺疊式功能表底下的下拉式清單。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的標記屬性。
1. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開 [!UICONTROL Cookies] 摺疊式功能表，便會顯示 [!UICONTROL Cookie 期限]下拉式清單。

此下拉式清單包含下列值：

* **預設值**：Cookie 會在 2 年後到期。
* **無**：AppMeasurement 不設定 Cookie。
* **作業階段**：Cookie 會在訪客的作業階段結束時到期。
* **秒**：Cookie 會在指定的秒數過後到期。例如，將此下拉式清單設定為[!UICONTROL 秒]，並將 `86400` 放入自訂欄位中，便會強制 Cookie 在 24 小時後到期。

## AppMeasurement中的s.cookieLifetime和Analytics擴展自定義代碼編輯器

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
