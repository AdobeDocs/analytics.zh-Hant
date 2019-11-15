---
description: 驗證已在您的網站上正確載入動態標籤管理程式庫。
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;verify code;verify header code;verify footer code;embed tab;embed
solution: Analytics
title: 驗證頁首與頁尾代碼
topic: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 驗證頁首與頁尾代碼

驗證已在您的網站上正確載入動態標籤管理程式庫。

1. 在瀏覽器中開啟您的網站。
1. 開啟[!UICONTROL 開發人員控制台]，方法是按一下滑鼠右鍵並選擇&#x200B;**[!UICONTROL 檢查元素]** &gt; **[!UICONTROL 控制台]**。
1. 按 **[!UICONTROL Enter]** 鍵。

   若已正確安裝程式碼，就會看到控制台顯示 *`true`*。

   如果未正確安裝代碼，您便會看到此參考錯誤:

   `_satellite is not defined`

   如果收到此錯誤，請確定:

* 您已在網站每個頁面的 [!DNL HEAD] 區段中包含完整的頁首程式碼，且該程式碼盡量在最接近 [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">]標籤的位置。
* 代碼片段中沒有出現非預期字元 (若出現非預期字元，可能是從格式化文件複製並貼過來的緣故)。

