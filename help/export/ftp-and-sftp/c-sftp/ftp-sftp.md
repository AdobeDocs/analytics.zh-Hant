---
description: SFTP 是一種傳輸資料的安全通訊協定，可確保除了您以外，其他人都看不到您的資料。Adobe 工程技術服務可以設定 SFTP 帳戶，安全地保留您的資料。
keywords: ftp;sftp
title: 安全檔案傳輸通訊協定 - 概觀
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 安全檔案傳輸通訊協定 - 概觀

SFTP 是一種傳輸資料的安全通訊協定，可確保除了您以外，其他人都看不到您的資料。Adobe 工程技術服務可以設定 SFTP 帳戶，安全地保留您的資料。

## 推送傳遞 {#section_A47831BB1DCA490BB57F0940617AA506}

這表示 Adobe 的伺服器將檔案「推送」至您的伺服器。本質上，我們是將檔案傳遞至您的端點。

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) 和 [ Analytics 資料摘要](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)可透過 SFTP 推送資料。

下列 Analytics 工具&#x200B;**無法**&#x200B;透過 SFTP 推送資料：

* Reports &amp; Analytics
* Ad Hoc Analysis
* Report Builder

## 提取傳遞 {#section_FA29FAEF02FE40B8B32452146A036F48}

這表示透過一般 FTP 將檔案傳送至其中一部 Adobe 伺服器。如果您想讓檔案存放在您的伺服器上，則需從您的伺服器向 Adobe FTP 伺服器使用 SFTP，將該檔案從 Adobe 伺服器上取下。您可使用下列三種方法其中之一來達成此目的:

* [不使用密碼透過 SFTP 連線至 Adobe。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [使用 SFTP 連線至 Adobe FTP 帳戶。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* 您可以將任何想要的報表推送至 Adobe FTP - 例如資料摘要/報告與分析/臨機等，接著再把它們取下。Adobe 無法將這些報表傳遞至您已設定的 SFTP 伺服器。

