---
description: 在 Adobe Analytics 中手動部署 Dynamic Tag Management 時插入 AppMeasurement 程式碼。
keywords: Dynamic Tag Management;linked accounts;linking accounts;edit code;appmeasurement;appmeasurement code
solution: Experience Cloud,Analytics,Target
title: 插入核心 AppMeasurement 程式碼
uuid: 3f83fbb1-3ed5-4e45-888a-0a183aac1a90
translation-type: tm+mt
source-git-commit: a4542164031fc9f181dfdc471a1d54b5056b1223
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 100%

---


# 插入核心 AppMeasurement 程式碼

在 Adobe Analytics 中手動部署 Dynamic Tag Management 時插入 AppMeasurement 程式碼。

1. 在 [!DNL Adobe Analytics] 工具頁面上，展開&#x200B;**[!UICONTROL 一般]**&#x200B;區段，然後按一下&#x200B;**[!UICONTROL 開啟編輯器]**。
1. 在[部署 Adobe Analytics](/help/implement/other/dtm/t-analytics-deploy.md)中，將您下載的 [!DNL AppMeasurement_JavaScript*.zip] 檔案解壓縮。

   如果您選擇使用自訂程式庫，當您開啟視窗，該視窗即會顯示最新的程式碼版本。不需從 Admin Console 下載 zip。
1. 在文字編輯器中開啟 [!DNL AppMeasurement.js]。
1. 將內容複製並貼到&#x200B;**[!UICONTROL 編輯程式碼]**&#x200B;視窗中。

   ![](assets/edit-code.png)

1. Adobe 建議在此區段上新增下列程式碼 *`Do Not Alter Anything Below This Line`*：

   ```
   var s_account="INSERT-RSID-HERE"
   var s=s_gi(s_account)
   ```

   >[!IMPORTANT]
   >
   >如果您新增此程式碼，建議您也在整體程式庫設定中選取&#x200B;**[!UICONTROL 使用以下的自訂程式碼設定報表套裝]**&#x200B;核取方塊。

1. 按一下&#x200B;**[!UICONTROL 儲存並關閉]**。

   如果您要使用媒體模組、整合模組或實施外掛程式，也可以將之複製到程式碼區域。Dynamic Tag Management 中的受管理程式碼完全可以像傳統實施中的 JavaScript 檔案一樣來設定。

