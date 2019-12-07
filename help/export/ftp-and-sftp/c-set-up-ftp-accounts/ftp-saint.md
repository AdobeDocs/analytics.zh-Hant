---
description: 分類 (SAINT) FTP 選項對於上傳大型分類資料集可提供更大彈性，包括能夠將資料上傳至多個報表套裝，以及可以上傳超過 50,000 列的資料集。
keywords: ftp;sftp
title: 分類
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 分類

分類FTP選項提供更大的彈性，可上傳大型分類資料集，包括將資料上傳至多個報表套裝以及上傳超過50,000列的資料集。

請參閱[分類](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html)，了解如何透過 FTP 下載分類資料以及如何透過 FTP 上傳資料檔案的步驟 (包括建立 FTP 帳戶的步驟)。

系統匯入這些檔案的所需時間因許多因素而異。如果上傳的檔案在 6 小時後仍存在 FTP 伺服器上，請與貴組織的受支援使用者合作、聯絡 Adobe 客戶服務。

成功的匯入可立即在匯出中顯示正確變更，但使用瀏覽器匯入的 Analytics 中資料變更可能需要 4 小時，而使用 FTP 匯入則可能需要高達 24 小時。

如需 FTP 限制和資料保留的相關資訊，請參閱[FTP 限制和資料保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## 關於分類和資料來源上傳的 .fin 檔案 {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL Data Source] file ( [!DNL .tab]or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. 此檔案的用途是告知系統，資料檔案已完全上傳至 FTP 帳戶。The [!DNL .fin] file lets Adobe recognize that you are done with your import. 在提交此檔案後，Adobe 會從 FTP 移除這兩個檔案，並開始處理匯入。匯入檔案: [!DNL Classifications.tab]

完成檔案： [!DNL Classifications.fin]

If you upload your Data Sources or classification file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. 除非您已在 Analytics「[!UICONTROL 建立 FTP 帳戶]」視窗的「[!UICONTROL 通知收件者]」中輸入您的電子郵件地址，否則不會收到此類狀況的通知。如果未在此欄位中輸入電子郵件地址，將不會傳送任何通知。

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. 如果發生這種狀況，系統會傳送通知給「[!UICONTROL 建立 FTP 帳戶]」視窗「[!UICONTROL 通知收件者]」欄位中所列出的電子郵件地址。如果未輸入電子郵件地址，將不會傳送任何通知。
