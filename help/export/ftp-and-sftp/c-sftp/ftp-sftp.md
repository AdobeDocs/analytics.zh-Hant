---
description: SFTP是一種傳輸資料的安全通訊協定，可確保任何人都看不到您的資料。Adobe工程技術服務可以設定SFTP帳戶，安全地保留您的資料。
keywords: ftp；sftp
seo-description: SFTP是一種傳輸資料的安全通訊協定，可確保任何人都看不到您的資料。Adobe工程技術服務可以設定SFTP帳戶，安全地保留您的資料。
seo-title: 安全檔案傳輸通訊協定-概觀
solution: Analytics
title: 安全檔案傳輸通訊協定-概觀
uuid: 7dd1a867-e828-4c7 b-bb11-75a81 d4 c149 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 安全檔案傳輸通訊協定-概觀

SFTP是一種傳輸資料的安全通訊協定，可確保任何人都看不到您的資料。Adobe工程技術服務可以設定SFTP帳戶，安全地保留您的資料。

## 推送傳遞 {#section_A47831BB1DCA490BB57F0940617AA506}

這表示 Adobe 的伺服器將檔案「推送」至您的伺服器。本質上，我們是將檔案傳遞至您的端點。

[資料倉儲](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md#concept_904ADB7B4FE04DCCB90EFDB6D0DB1076) 和 [Analytics資料饋送](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) 可透過SFTP推送資料。

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Report Builder

## 提取傳遞 {#section_FA29FAEF02FE40B8B32452146A036F48}

這表示透過一般 FTP 將檔案傳送至其中一部 Adobe 伺服器。如果您想要在伺服器上使用檔案，則必須從您的伺服器將SFTP從伺服器移至Adobe的FTP伺服器。您可使用下列三種方法其中之一來達成此目的:

* [不需密碼即可透過SFTP連線至Adobe。](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846)
* [使用SFTP連線至Adobe FTP帳戶。](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md#concept_01176600188441C6AFB28F5E264D89F8)
* 您可以將任何想要的報表推送至 Adobe FTP - 例如資料饋送/報告與分析/臨機等，接著再把它們取下。Adobe無法將這些報告傳送至您已設定的SFTP伺服器。

