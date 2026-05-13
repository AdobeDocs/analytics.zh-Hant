---
description: 您可以使用 Analytics 建立及管理 FTP 型資料來源，其會利用 FTP 檔案轉移，將離線或歷史資料匯入 Experience Cloud。
keywords: ftp;sftp
title: 資料來源概觀
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
TQID: https://experienceleague.adobe.com/Mq4r5p1872tIxfjts7HOq50XWky12Oy4fTi9ajzbAsc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 63%

---

# FTP型資料來源

您可以使用 Analytics 建立及管理 FTP 型資料來源，其會利用 FTP 檔案轉移，將離線或歷史資料匯入 Experience Cloud。

建立資料來源例項後，工具會提供一個FTP位置，供您上傳資料來源檔案。 上傳完成之後，Data Sources會自動尋找及處理這些專案。 處理檔案後，資料即可用於Analytics報表。

「資料來源管理員」中的「[!UICONTROL 建立]」索引標籤可讓您為所選報表套裝設定新的資料來源實例。 [!UICONTROL 資料來源精靈]會引導您完成建立資料來源範本的過程，並建立上傳資料的FTP位置。

在[!UICONTROL 管理資料來源]視窗中，尋找您的資料來源並選取FTP資訊連結。 您的FTP登入資訊會顯示在[!UICONTROL 上傳/FTP資訊]區段的[!UICONTROL 啟用資料Source]視窗中。

如需FTP限制和資料保留的詳細資訊，請參閱[FTP限制和資料保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## 關於分類和資料來源上傳的 .fin 檔案 {#section_1484719F8A134EAE91212DBD8F15174F}

上傳分類或[!UICONTROL 資料來源]檔案 ([!DNL .tab] 或 [!DNL .txt]) 時，還需要上傳與正在匯入的資料檔案具有相同名稱，但副檔名為 [!DNL .fin] 的空白檔案。 此 [!DNL .fin] 檔案是完成檔案。 此檔案的用途是告知系統，資料檔案已完全上傳至 FTP 帳戶。 [!DNL .fin] 檔案可讓 Adobe 識別您已完成匯入作業。 在提交此檔案後，Adobe 會從 FTP 移除這兩個檔案，並開始處理匯入。
匯入檔案：[!DNL Classifications.tab]

完成檔案：[!DNL Classifications.fin]

如果您上傳的資料來源或 SAINT 檔案未附帶 [!DNL .fin] 檔案，Adobe 不會將其新增至處理佇列。 檔案仍保留在 FTP 上，不會套用至您在 [!UICONTROL Experience Cloud] 中的資料。 只有在您於[!UICONTROL 建立FTP帳戶]報告視窗中輸入電子郵件地址作為[!UICONTROL 通知收件者]時，才會通知您。 若未在此欄位輸入電子郵件地址，則不會傳送任何通知。

如果您上傳檔案時已附帶 [!DNL .fin] 檔案，但檔案中發生錯誤，則系統會提交該檔案以進行處理，但錯誤會導致處理停止，並將檔案傳送至錯誤資料夾。 如果發生這種狀況，系統會傳送通知給「[!UICONTROL 建立 FTP 帳戶]」視窗內「[!UICONTROL 通知收件者]」欄位中所列出的電子郵件地址。 如果未輸入電子郵件地址，則不會傳送通知。
