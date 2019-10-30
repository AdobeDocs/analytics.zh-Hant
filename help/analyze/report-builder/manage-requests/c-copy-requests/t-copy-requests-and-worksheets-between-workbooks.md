---
description: 將來源活頁簿中的整份試算表複製到一或多份目標活頁簿中。
seo-description: 將來源活頁簿中的整份試算表複製到一或多份目標活頁簿中。
seo-title: 在活頁簿之間複製請求和工作表
solution: Analytics
title: 在活頁簿之間複製請求和工作表
topic: Report Builder
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 在活頁簿之間複製請求和工作表

將來源活頁簿中的整份試算表複製到一或多份目標活頁簿中。

若要進行這項作業，您必須在同一個的 Excel 例項中至少開啟兩個活頁簿: 第一個來源活頁簿包含的試算表 (工作表) 其請求已映射儲存格，另一個目標活頁簿則是做為目標。對於每個新的目標活頁簿，您應該先登入與來源活頁簿相同的報表套裝，接著再貼上含有請求的試算表。
1. Right-click the spreadsheet in the source workbook and select **[!UICONTROL Copy Worksheet w/Requests]**.
1. In the destination workbook, right-click the spreadsheet and select **[!UICONTROL Paste Worksheet w/Requests]**.

   同一個 Excel 例項表示在同一時間內，只有一個 Excel 程序 ([!DNL excel.exe])在電腦中運作。如果您啟動兩個 Excel 例項並嘗試從第一個 Excel 例項將活頁簿中的工作表複製到第二個 Excel 例項的活頁簿中，Report Builder 不會在第二個 Excel 例項的捷徑功能表中提供貼上工作表選項。

   如果您登入使用不同報表套裝的來源和目標活頁簿，貼上作業的結果僅限影響目標活頁簿格式的項目。Report Builder 會顯示一則訊息，指出衍生自指定報表套裝 (位於來源活頁簿中) 的請求資訊不適用於目標活頁簿。若要揭示貼入目標活頁簿的請求，您登入的目標活頁簿必須使用與來源活頁簿相同的報表套裝。

   您可以將某個活頁簿之試算表中的一或多個請求複製及貼入另一個活頁簿的試算表，只要第二個活頁簿在同一個 Excel 例項中是以另一份文件方式開啟即可。這兩個活頁簿中的請求都必須以相同的報表套裝登入來建立。
