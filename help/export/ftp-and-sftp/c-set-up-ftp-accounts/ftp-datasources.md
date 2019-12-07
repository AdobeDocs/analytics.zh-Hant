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

「資料來源管理器」中的「[!UICONTROL 建立]」索引標籤可讓您為所選報表套裝設定新的資料來源實例。「[!UICONTROL 資料來源精靈]」將引導您完成建立資料來源範本的整個過程，並將建立一個上傳資料的 FTP 地址。

在「[!UICONTROL 管理資料來源]」視窗中，尋找資料來源與選取 FTP 資訊連結。您的 FTP 登入資訊會顯示在「[!UICONTROL 啟動資料來源]」視窗的「[!UICONTROL 上載/FTP 資訊]」區段中。

如需 FTP 限制和資料保留的相關資訊，請參閱[FTP 限制和資料保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## 關於分類和資料來源上傳的 .fin 檔案 {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. 此檔案的用途是告知系統，資料檔案已完全上傳至 FTP 帳戶。The [!DNL .fin] file lets Adobe recognize that you are done with your import. 在提交此檔案後，Adobe 會從 FTP 移除這兩個檔案，並開始處理匯入。匯入檔案: [!DNL Classifications.tab]

完成檔案： [!DNL Classifications.fin]

If you upload your Data Sources or SAINT file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. 除非您已在報告「[!UICONTROL 建立 FTP 帳戶]」視窗的「[!UICONTROL 通知收件者]」中輸入您的電子郵件地址，否則不會收到此類狀況的通知。如果未在此欄位中輸入電子郵件地址，將不會傳送任何通知。

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. 如果發生這種狀況，系統會傳送通知給「[!UICONTROL 建立 FTP 帳戶]」視窗「[!UICONTROL 通知收件者]」欄位中所列出的電子郵件地址。如果未輸入電子郵件地址，將不會傳送任何通知。
