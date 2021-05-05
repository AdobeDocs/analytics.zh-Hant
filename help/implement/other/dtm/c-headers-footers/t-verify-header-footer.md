---
description: 驗證已在您的網站上正確載入動態標籤管理程式庫。
keywords: Analytics 實施;實施方法;Dynamic Tag Management;DTM;程式碼;頁面程式碼;頁首程式碼;頁尾程式碼;內嵌程式碼;驗證程式碼;驗證頁首程式碼;驗證頁尾程式碼;內嵌標籤;內嵌
title: 驗證頁首與頁尾代碼
topic-fix: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
exl-id: bed44ba7-8e0e-49e2-bedc-fb1ba66e5b18
translation-type: ht
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: ht
source-wordcount: '162'
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
