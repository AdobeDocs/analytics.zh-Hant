---
description: SFTP是傳輸資料的安全通訊協定，可確保除了您以外，沒有人能看見您的資料。 Adobe工程服務可以設定SFTP帳戶，以安全地保留您的資料。
keywords: ftp;sftp
title: 安全檔案傳輸通訊協定 - 概觀
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 安全檔案傳輸通訊協定 - 概觀

SFTP是傳輸資料的安全通訊協定，可確保除了您以外，沒有人能看見您的資料。 Adobe工程服務可以設定SFTP帳戶，以安全地保留您的資料。

## 推送傳遞 {#section_A47831BB1DCA490BB57F0940617AA506}

這表示 Adobe 的伺服器將檔案「推送」至您的伺服器。本質上，我們是將檔案傳遞至您的端點。

[資料倉庫](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) 和 [](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) Analytics資料饋送可以透過SFTP推播資料。

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Report Builder

## 提取傳遞 {#section_FA29FAEF02FE40B8B32452146A036F48}

這表示透過一般 FTP 將檔案傳送至其中一部 Adobe 伺服器。如果您想要將檔案放在伺服器上，就必須使用SFTP從伺服器將檔案從Adobe的伺服器上取出至Adobe的FTP伺服器。 您可使用下列三種方法其中之一來達成此目的:

* [不使用密碼透過 SFTP 連線至 Adobe.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [使用SFTP連線至Adobe FTP帳戶。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* 您可以將任何想要的報表推送至 Adobe FTP - 例如資料饋送/報告與分析/臨機等，接著再把它們取下。Adobe無法將這些報表傳送至您所設定的SFTP伺服器。

