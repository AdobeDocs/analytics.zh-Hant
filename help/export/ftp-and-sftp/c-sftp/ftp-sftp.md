---
description: SFTP 是一種傳輸資料的安全通訊協定，可確保除了您以外，其他人都看不到您的資料。 Adobe 工程技術服務可以設定 SFTP 帳戶，安全地保留您的資料。
keywords: ftp;sftp
title: 安全檔案傳輸通訊協定 - 概觀
feature: FTP Export
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
TQID: https://experienceleague.adobe.com/kJYtQSuxz-2NMUYqZb01wsr6ltQQbD5itpPYYzsmlCM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 220
ht-degree: 80%

---

# 安全檔案傳輸通訊協定 - 概觀

SFTP是一種傳輸資料的安全通訊協定，可確保除了您以外，其他人都看不到您的資料。 Adobe 工程技術服務可以設定 SFTP 帳戶，安全地保留您的資料。

## 推送傳遞 {#section_A47831BB1DCA490BB57F0940617AA506}

這表示Adobe的伺服器「推送」檔案至您的伺服器。 基本上，我們會將其傳送至您的端點。

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) 和 [ Analytics 資料摘要](/help/export/analytics-data-feed/data-feed-overview.md)可透過 SFTP 推送資料。

Report Builder **無法透過SFTP**&#x200B;推送資料。

## 提取傳遞 {#section_FA29FAEF02FE40B8B32452146A036F48}

這表示透過一般 FTP 將檔案傳送至其中一部 Adobe 伺服器。 如果您想讓檔案存放在您的伺服器上，則需從您的伺服器向 Adobe FTP 伺服器使用 SFTP，將該檔案從 Adobe 伺服器上取下。 您可使用下列三種方法達成此目的：

* [不使用密碼透過 SFTP 連線至 Adobe。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [使用 SFTP 連線至 Adobe FTP 帳戶。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* 您可以將任何需要的報表推送至 Adobe FTP (例如資料摘要/R&amp;A/臨機等)，接著再加以提取。 Adobe 無法將這些報表傳遞至您已設定的 SFTP 伺服器。
