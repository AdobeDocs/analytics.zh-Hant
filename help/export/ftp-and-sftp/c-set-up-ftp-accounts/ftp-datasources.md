---
description: 您可以使用 Analytics 建立及管理 FTP 型資料來源，其會利用 FTP 檔案轉移，將離線或歷史資料匯入 Experience Cloud。
keywords: ftp;sftp
title: 資料來源概觀
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
source-git-commit: 7dc97ad5225baf56c829efc8c21b07154bdd8ff9
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 96%

---

# FTP型資料來源

您可以使用 Analytics 建立及管理 FTP 型資料來源，其會利用 FTP 檔案轉移，將離線或歷史資料匯入 Experience Cloud。

建立資料來源例項後，此工具會提供您用來上傳資料來源檔案的 FTP 位置。上傳後，Data Sources 會自動找到檔案並處理它們。檔案處理完畢後，此資料便可供分析報表使用。

「資料來源管理員」中的「[!UICONTROL 建立]」索引標籤可讓您為所選報表套裝設定新的資料來源實例。「[!UICONTROL 資料來源精靈]」將引導您完成建立資料來源範本的整個過程，並將建立一個上傳資料的 FTP 地址。

在「[!UICONTROL 管理資料來源]」視窗中，尋找資料來源與選取 FTP 資訊連結。您的 FTP 登入資訊會顯示在「[!UICONTROL 啟動資料來源]」視窗的「[!UICONTROL 上載/FTP 資訊]」區段中。

如需FTP限制和資料保留的詳細資訊，請參閱[FTP限制和資料保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## 關於分類和資料來源上傳的 .fin 檔案 {#section_1484719F8A134EAE91212DBD8F15174F}

上傳分類或[!UICONTROL 資料來源]檔案 ([!DNL .tab] 或 [!DNL .txt]) 時，還需要上傳與正在匯入的資料檔案具有相同名稱，但副檔名為 [!DNL .fin] 的空白檔案。此 [!DNL .fin] 檔案是完成檔案。此檔案的用途是告知系統，資料檔案已完全上傳至 FTP 帳戶。[!DNL .fin] 檔案可讓 Adobe 識別您已完成匯入作業。在提交此檔案後，Adobe 會從 FTP 移除這兩個檔案，並開始處理匯入。匯入檔案：[!DNL Classifications.tab]

完成檔案：[!DNL Classifications.fin]

如果您上傳的資料來源或 SAINT 檔案未附帶 [!DNL .fin] 檔案，Adobe 不會將其新增至處理佇列。檔案仍保留在 FTP 上，不會套用至您在 [!UICONTROL Experience Cloud] 中的資料。除非您已在報告「[!UICONTROL 建立 FTP 帳戶]」視窗的「[!UICONTROL 通知收件者]」中輸入您的電子郵件地址，否則不會收到此類狀況的通知。如果未在此欄位中輸入電子郵件地址，將不會傳送任何通知。

如果您上傳檔案時已附帶 [!DNL .fin] 檔案，但檔案中發生錯誤，則系統會提交該檔案以進行處理，但錯誤會導致處理停止，並將檔案傳送至錯誤資料夾。如果發生這種狀況，系統會傳送通知給「[!UICONTROL 建立 FTP 帳戶]」視窗內「[!UICONTROL 通知收件者]」欄位中所列出的電子郵件地址。 如果未輸入電子郵件地址，將不會傳送任何通知。
