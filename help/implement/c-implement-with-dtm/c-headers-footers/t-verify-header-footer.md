---
description: 驗證已在您的網站上正確載入動態標籤管理程式庫。
keywords: Analytics實作；實施方法；動態標籤管理；dtm；程式碼；頁面程式碼；頁首代碼；頁尾代碼；內嵌代碼；驗證程式碼；驗證頁首代碼；確認頁尾代碼；內嵌索引標籤；內嵌內嵌
seo-description: 驗證已在您的網站上正確載入動態標籤管理程式庫。
seo-title: 驗證頁首與頁尾代碼
solution: Analytics
title: 驗證頁首與頁尾代碼
topic: 開發人員和實施
uuid: d395a417-0c61-41a6-a124-d2 f400 f4626 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 驗證頁首與頁尾代碼

驗證已在您的網站上正確載入動態標籤管理程式庫。

1. 在瀏覽器中開啟您的網站。
1. Open the [!UICONTROL Developer Console] by right-clicking and choosing **[!UICONTROL Inspect Element]** &gt; **[!UICONTROL Console]**.
1. Press **[!UICONTROL Enter]**.

   If the code was properly installed, you will see *`true`* display in the console.

   如果未正確安裝代碼，您便會看到此參考錯誤:

   `_satellite is not defined`

   如果收到此錯誤，請確定:

* You have included the full header code on every page of the site in the [!DNL HEAD] section, as close to the [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">]標籤的位置。
* 代碼片段中沒有出現非預期字元 (若出現非預期字元，可能是從格式化文件複製並貼過來的緣故)。

