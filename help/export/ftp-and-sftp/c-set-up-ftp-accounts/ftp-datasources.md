---
description: 您可以使用 Analytics 建立及管理 FTP 型資料來源，其會利用 FTP 檔案轉移，將離線或歷史資料匯入 Experience Cloud。
keywords: ftp;sftp
title: 資料來源
uuid: 41ba2de7-d33d-4394-b7d8-04a116f45419
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 資料來源

您可以使用 Analytics 建立及管理 FTP 型資料來源，其會利用 FTP 檔案轉移，將離線或歷史資料匯入 Experience Cloud。

建立資料來源例項後，此工具會提供您用來上傳資料來源檔案的 FTP 位置。上傳後，Data Sources 會自動找到檔案並處理它們。檔案處理完畢後，此資料便可供分析報表使用。

The [!UICONTROL Create] tab in the Data Sources Manager lets you configure a new Data Sources instance for the selected report suite. The [!UICONTROL Data Sources Wizard] guides you through the process of creating a Data Sources template, and creates an FTP location for uploading data.

In the [!UICONTROL Manage Data Sources] window, find your data source and select the FTP Info link. 您的FTP登入資訊會顯示在區 [!UICONTROL Activate a Data Source] 段的視窗 [!UICONTROL Upload/FTP Information] 中。

如需FTP限制和資料保留的詳細資訊，請參 [閱FTP限制和資料保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## 關於分類和資料來源上傳的 .fin 檔案 {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. 此 [!DNL .fin] 檔案是完成檔案。此檔案的用途是告知系統，資料檔案已完全上傳至 FTP 帳戶。[!DNL .fin] 檔案可讓 Adobe 識別您已完成匯入作業。在提交此檔案後，Adobe 會從 FTP 移除這兩個檔案，並開始處理匯入。匯入檔案：[!DNL Classifications.tab]

完成檔案：[!DNL Classifications.fin]

如果您上傳的資料來源或 SAINT 檔案未附帶 [!DNL .fin] 檔案，Adobe 不會將其新增至處理佇列。檔案仍保留在 FTP 上，不會套用至您在 [!UICONTROL Experience Cloud] 中的資料。You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of reporting. 如果未在此欄位中輸入電子郵件地址，將不會傳送任何通知。

如果您上傳檔案時已附帶 [!DNL .fin] 檔案，但檔案中發生錯誤，則系統會提交該檔案以進行處理，但錯誤會導致處理停止，並將檔案傳送至錯誤資料夾。If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. 如果未輸入電子郵件地址，將不會傳送任何通知。
