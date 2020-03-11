---
description: 資料摘要是將 Adobe 收到的點按資料流資料匯出，可同時提供標準和自訂資料摘要。
keywords: ftp;sftp
title: 資料摘要
uuid: 3c70eea3-ca59-4aa5-9b11-64e1bb677bfa
translation-type: ht
source-git-commit: fc14751c810019c5257a23a8a598b16f42ed10ee

---


# 資料摘要

資料摘要是將 Adobe 收到的點按資料流資料匯出，可同時提供標準和自訂[資料摘要](/help/export/analytics-data-feed/data-feed-overview.md)。

如果您已購買 Adobe Data Warehouse，[!UICONTROL 標準資料摘要]您可以設定自己的 Analytics 資料摘要。可將其設定為傳送至任何 FTP 帳戶 (由 Adobe 設定的帳戶或外部 FTP 皆可)。Adobe 工程技術服務提供自訂的[!UICONTROL 資料摘要]，幾乎可透過所有方法進行傳送。

[!UICONTROL 資料摘要]FTP 帳戶允許 10GB (依預設)。所有其他標準 FTP 帳戶 則預設為 50MB。將 FTP 帳戶用於正確用途的客戶，有時候某些高流量的使用者，會很快就裝滿其帳戶。當 FTP 帳戶已滿，就無法再推送檔案至該帳戶。因此，傳遞至該 FTP 帳戶的任何檔案 ([!UICONTROL 資料摘要]、資料倉庫請求等) 將停止傳遞。因此，請務必移除已接收和下載的檔案，適當管理您的 Adobe FTP 帳戶。

當 FTP 帳戶已滿時，您應下載並移除目前的檔案，並通知 Adobe 已清除空間。接著 Adobe 就能重新傳送尚未傳遞的檔案。有些工具 (例如資料倉庫) 可讓使用者重新傳送這些檔案。重新傳送也許無須 Adobe 介入。如果您的 FTP 帳戶似乎經常填滿，請聯絡 Adobe 客戶服務，由他們推薦一些傳遞替代方案，包括提高 FTP 空間以及該帳戶的檔案數目配額。
