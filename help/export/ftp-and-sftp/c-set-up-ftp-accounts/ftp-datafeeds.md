---
description: 資料摘要是將 Adobe 收到的點按資料流資料匯出，可同時提供標準和自訂資料摘要。
keywords: ftp;sftp
title: 資料摘要
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
source-git-commit: 05b4dc07de567b25e71b47fd92743bee0b5621f8
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 82%

---

# 資料摘要

>[!NOTE]
>
>以下資訊與FTP和SFTP目的地型別有關。 FTP和SFTP是舊有的目的地型別。 設定資料摘要時，您應使用較安全的雲端目的地型別。 如需為資料摘要設定雲端目的地型別的詳細資訊，請參閱[建立資料摘要](/help/export/analytics-data-feed/create-feed.md)。

資料摘要是將 Adobe 收到的點按資料流資料匯出，可同時提供標準和自訂[資料摘要](/help/export/analytics-data-feed/data-feed-overview.md)。

如果您已購買 Adobe Data Warehouse，[!UICONTROL 標準資料摘要]您可以設定自己的 Analytics 資料摘要。可將其設定為傳送至任何 FTP 帳戶 (由 Adobe 設定的帳戶或外部 FTP 皆可)。Adobe 工程技術服務提供自訂的[!UICONTROL 資料摘要]，幾乎可透過所有方法進行傳送。

[!UICONTROL 資料摘要] FTP帳戶允許10GB （預設值）。 所有其他標準 FTP 帳戶 則預設為 50MB。將 FTP 帳戶用於正確用途的客戶，有時候某些高流量的使用者，會很快就裝滿其帳戶。當 FTP 帳戶已滿，就無法再推送檔案至該帳戶。因此，傳遞至該 FTP 帳戶的任何檔案 ([!UICONTROL 資料摘要]、資料倉庫請求等) 將停止傳遞。因此，請務必移除已接收和下載的檔案，適當管理您的 Adobe FTP 帳戶。

當 FTP 帳戶已滿時，您應下載並移除目前的檔案，並通知 Adobe 已清除空間。接著 Adobe 就能重新傳送尚未傳遞的檔案。有些工具 (例如資料倉庫) 可讓使用者重新傳送這些檔案。重新傳送也許無須 Adobe 介入。如果您的 FTP 帳戶似乎經常填滿，請聯絡 Adobe 客戶服務，由他們推薦一些傳遞替代方案，包括提高 FTP 空間以及該帳戶的檔案數目配額。
