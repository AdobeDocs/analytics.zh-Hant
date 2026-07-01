---
description: 您可以使用Analytics建立及管理FTP型資料來源，其會利用FTP檔案傳輸，將離線或歷史資料匯入CX Enterprise。
keywords: ftp;sftp
title: 資料來源概觀
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
TQID: 'https://experienceleague.adobe.com/3i-ms9Q49CUmEwXiQLek15S3-Kvvh0IIv19-hm01EN0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: e681610c8238aa4940053a28ee60ea54492cba8b
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 40%

---

# FTP型資料來源

您可以使用Analytics建立及管理FTP型資料來源，其會利用FTP檔案傳輸，將離線或歷史資料匯入CX Enterprise。

建立資料來源例項後，工具會提供一個FTP位置，供您上傳資料來源檔案。 上傳完成之後，Data Sources會自動尋找及處理這些專案。 處理檔案後，資料即可用於Analytics報表。

「資料來源管理員」中的「[!UICONTROL 建立]」索引標籤可讓您為所選報表套裝設定新的資料來源實例。 資料來源精靈會引導您完成建立資料來源範本的過程，並建立用於上傳資料的FTP位置。

在[!UICONTROL 管理資料來源]視窗中，尋找您的資料來源並選取FTP資訊連結。 您的FTP登入資訊會顯示在[!UICONTROL 上傳/FTP資訊]區段的[!UICONTROL 啟用資料Source]視窗中。

如需FTP限制和資料保留的詳細資訊，請參閱[FTP限制和資料保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## 關於分類和資料來源上傳的 .fin 檔案 {#section_1484719F8A134EAE91212DBD8F15174F}

上傳分類或資料來源檔案（`.tab`或`.txt`）時，還需要上傳與正在匯入的資料檔案具有相同名稱，但副檔名為`.fin`的空白檔案。 此 `.fin` 檔案是完成檔案。 此檔案的用途是告知系統，資料檔案已完全上傳至 FTP 帳戶。 `.fin` 檔案可讓 Adobe 識別您已完成匯入作業。 在提交此檔案後，Adobe 會從 FTP 移除這兩個檔案，並開始處理匯入。

匯入檔案：`Classifications.tab`

完成檔案：`Classifications.fin`

如果您上傳的資料來源或 SAINT 檔案未附帶 `.fin` 檔案，Adobe 不會將其新增至處理佇列。 檔案仍保留在FTP上，不會套用至您在CX Enterprise中的資料。 只有在您於[!UICONTROL 建立FTP帳戶]報告視窗中輸入電子郵件地址作為[!UICONTROL 通知收件者]時，才會通知您。 若未在此欄位輸入電子郵件地址，則不會傳送任何通知。

如果您上傳檔案時已附帶 `.fin` 檔案，但檔案中發生錯誤，則系統會提交該檔案以進行處理，但錯誤會導致處理停止，並將檔案傳送至錯誤資料夾。 如果發生這種狀況，系統會傳送通知給「[!UICONTROL 建立 FTP 帳戶]」視窗內「[!UICONTROL 通知收件者]」欄位中所列出的電子郵件地址。 如果未輸入電子郵件地址，則不會傳送通知。
