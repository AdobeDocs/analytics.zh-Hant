---
description: 驗證已在您的網站上正確載入 Dynamic Tag Management 程式庫。
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;verify code;verify header code;verify footer code;embed tab;embed
title: 驗證頁首與頁尾代碼
topic: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: tm+mt
source-git-commit: 82cf5ddfd4d18af09c2dbedba20514e4b643a94b
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 100%

---


# 驗證頁首與頁尾代碼

驗證已在您的網站上正確載入 Dynamic Tag Management 程式庫。

1. 在瀏覽器中開啟您的網站。
1. 開啟[!UICONTROL 「開發人員主控台」]，方法是按一下滑鼠右鍵並選擇&#x200B;**[!UICONTROL 「檢查元素]** > **[!UICONTROL 主控台」]**。
1. 按 **[!UICONTROL Enter]** 鍵。

   若已正確安裝程式碼，就會看到主控台顯示 *`true`*。

   如果未正確安裝代碼，您便會看到此參考錯誤：

   `_satellite is not defined`

   如果收到此錯誤，請確定：

* 您已在網站每個頁面的 [!DNL HEAD] 區段中包含完整的頁首程式碼，且該程式碼盡量在最接近 `<head>` 標籤的位置。
* 代碼片段中沒有出現非預期字元 (若出現非預期字元，可能是從格式化文件複製並貼過來的緣故)。

