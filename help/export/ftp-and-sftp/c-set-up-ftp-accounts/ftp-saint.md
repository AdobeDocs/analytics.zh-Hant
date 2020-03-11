---
description: 分類 (SAINT) FTP 選項對於上傳大型分類資料集可提供更大彈性，包括能夠將資料上傳至多個報表套裝，以及可以上傳超過 50,000 列的資料集。
keywords: ftp;sftp
title: 分類
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 分類

分類 FTP 選項對於上傳大型分類資料集可提供更大彈性，包括能夠將資料上傳至多個報表套裝，以及可以上傳超過 50,000 列的資料集。

請參閱[分類](https://marketing.adobe.com/resources/help/zh_TW/reference/c_working_with_saint.html)，了解如何透過 FTP 下載分類資料以及如何透過 FTP 上傳資料檔案的步驟 (包括建立 FTP 帳戶的步驟)。

系統匯入這些檔案的所需時間因許多因素而異。如果上傳的檔案在 6 小時後仍存在 FTP 伺服器上，請與貴組織的受支援使用者合作、聯絡 Adobe 客戶服務。

成功的匯入可立即在匯出中顯示正確變更，但使用瀏覽器匯入的 Analytics 中資料變更可能需要 4 小時，而使用 FTP 匯入則可能需要高達 24 小時。

如需 FTP 限制和資料保留的相關資訊，請參閱 [FTP 限制和資料保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## 關於分類和資料來源上傳的 .fin 檔案 {#section_1484719F8A134EAE91212DBD8F15174F}

上傳分類或[!UICONTROL 資料來源]檔案 ([!DNL .tab] 或 [!DNL .txt]) 時，還需要上傳與正在匯入的資料檔案具有相同名稱，但副檔名為 [!DNL .fin] 的空白檔案。此 [!DNL .fin] 檔案是完成檔案。此檔案的用途是告知系統，資料檔案已完全上傳至 FTP 帳戶。[!DNL .fin] 檔案可讓 Adobe 識別您已完成匯入作業。在提交此檔案後，Adobe 會從 FTP 移除這兩個檔案，並開始處理匯入。匯入檔案：[!DNL Classifications.tab]

完成檔案：[!DNL Classifications.fin]

如果您上傳的資料來源或分類檔案未附帶 [!DNL .fin] 檔案，Adobe 不會將其新增至處理佇列。檔案仍保留在 FTP 上，不會套用至您在 [!UICONTROL Experience Cloud] 中的資料。除非您已在 Analytics「[!UICONTROL 建立 FTP 帳戶]」視窗的「[!UICONTROL 通知收件者]」中輸入您的電子郵件地址，否則不會收到此類狀況的通知。如果未在此欄位中輸入電子郵件地址，將不會傳送任何通知。

如果您上傳檔案時已附帶 [!DNL .fin] 檔案，但檔案中發生錯誤，則系統會提交該檔案以進行處理，但錯誤會導致處理停止，並將檔案傳送至錯誤資料夾。如果發生這種狀況，系統會傳送通知給「[!UICONTROL 建立 FTP 帳戶]」視窗「[!UICONTROL 通知收件者]」欄位中所列出的電子郵件地址。如果未輸入電子郵件地址，將不會傳送任何通知。
