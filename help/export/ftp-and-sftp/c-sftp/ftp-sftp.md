---
description: SFTP 是一種傳輸資料的安全通訊協定，可確保除了您以外，其他人都看不到您的資料。Adobe 工程技術服務可以設定 SFTP 帳戶，安全地保留您的資料。
keywords: ftp;sftp
title: 安全檔案傳輸通訊協定 - 概觀
feature: FTP Export
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 88%

---

# 安全檔案傳輸通訊協定 - 概觀

SFTP是一種傳輸資料的安全通訊協定，可確保除了您以外，其他人都看不到您的資料。 Adobe 工程技術服務可以設定 SFTP 帳戶，安全地保留您的資料。

## 推送傳遞 {#section_A47831BB1DCA490BB57F0940617AA506}

這表示 Adobe 的伺服器將檔案「推送」至您的伺服器。本質上，我們是將檔案傳遞至您的端點。

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) 和 [ Analytics 資料摘要](/help/export/analytics-data-feed/data-feed-overview.md)可透過 SFTP 推送資料。

Report Builder **無法透過SFTP**&#x200B;推送資料。

## 提取傳遞 {#section_FA29FAEF02FE40B8B32452146A036F48}

這表示透過一般 FTP 將檔案傳送至其中一部 Adobe 伺服器。如果您想讓檔案存放在您的伺服器上，則需從您的伺服器向 Adobe FTP 伺服器使用 SFTP，將該檔案從 Adobe 伺服器上取下。您可使用下列三種方法達成此目的：

* [不使用密碼透過 SFTP 連線至 Adobe。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [使用 SFTP 連線至 Adobe FTP 帳戶。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* 您可以將任何需要的報表推送至 Adobe FTP (例如資料摘要/R&amp;A/臨機等)，接著再加以提取。Adobe 無法將這些報表傳遞至您已設定的 SFTP 伺服器。
