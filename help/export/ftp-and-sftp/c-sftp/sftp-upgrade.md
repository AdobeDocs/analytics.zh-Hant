---
title: SFTP 服務升級 - 常見問題
description: 有關規劃 SFTP 服務升級的常見問題。
feature: FTP Export
exl-id: e271b545-0769-4a69-9d7f-dc46bc654737
TQID: https://experienceleague.adobe.com/HKI-iOTx-gHbsmL8BJszgs5e5nlflk67s64eqs2dd-k
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 444
ht-degree: 95%

---

# SFTP 服務升級 - 常見問題

在 2022 年 9 月 20 日，Adobe Analytics 將會升級其安全檔案傳輸通訊協定 ([SFTP]) 服務，以提供改良的檔案傳輸安全性功能。 在這次變更後，我們將不再支援某些 SFTP 用戶端設定。 這只會影響使用 SFTP 傳送給 Adobe Analytics 或從中擷取的資料。 FTP 通訊協定將不受影響。 為避免服務中斷，請確保您的 SFTP 用戶端 (程式碼、工具、服務) 將符合以下詳述的變更。

## 我要如何判斷我的組織目前正在使用哪些演算法、連線類型和通訊協定？

您正在使用的 FTP/SFTP 軟體應該會指示您為了與 Adobe Analytics 交換資料而在設定的連線中使用哪些特定的設定。 此軟體應該也會包含可供連線使用的不同選項的相關文件。 在這次更新後將受到支援的選項已在業界受到廣泛的支持和接納。

將被移除的連線選項通常被認為是過時的，不會用於目前的軟體。 如果您在過去三年內曾經升級 FTP/SFTP 軟體，這表示您可能已經有相容的連線。

## 哪些 Adobe Analytics 功能會使用 SFTP 來擷取資料？

以下功能提供使用 SFTP 將資料上傳到 Adobe Analytics 的選項。

* [分類](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)

* [客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=zh-Hant)

* [資料摘要](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)

* [資料來源](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)

* [Data Warehouse 傳遞的報表](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)

* 此外，某些透過[工程服務](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md)建立的自訂實作也可能會使用 SFTP 與 Adobe 交換資料。

## 這次更新將包含哪些特定的變更？

底下詳細清單列出將移除和將移除的連線和演演算法
支援：

* SFTP 通訊協定 mac 演算法：

   * 我們將不再支援：hmac-md5、hmac-md5-96、hmac-ripemd160、hmacripemd160@openssh.com、hmac-sha1、hmac-sha1-96、hmac-sha1-etm@openssh.com、umac-64-etm@openssh.com、umac-64@openssh.com

   * 我們將僅支援：hmac-sha2-512-etm@openssh.com、hmac-sha2-256-etm@openssh.com、umac-128-etm@openssh.com、hmac-sha2-512、hmacsha2-256、umac-128@openssh.com

* SFTP 通訊協定 ciphers 演算法：

   * 我們將不再支援：3des-cbc、aes128-cbc、aes128-gcm@openssh.com、aes192-cbc、aes256-cbc、aes256-gcm@openssh.com、arcfour、arcfour128、arcfour256、blowfish-cbc、cast128-cbc、rijndael-cbc@lysator.liu.se

   * 我們將僅支援：aes128-ctr、aes192-ctr、aes256-ctr

* SFTP 通訊協定支援的連線：

   * 我們將不再支援 scp 和 rsync 命令的使用或透過 sftp 通訊協定建立連線

   * 我們將僅支援單純的 SFTP 通訊協定連線

* 支援的 FTP/SFTP 用戶端/通訊協定：

   * FTP：vsftpd 版本 3.0.2-25 或更高版本

   * SFTP：openssh 版本 7.4p1-21 或更高版本
