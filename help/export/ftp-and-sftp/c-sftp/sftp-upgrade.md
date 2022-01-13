---
title: SFTP服務升級 — 常見問題集
description: 2022年5月計畫SFTP服務升級的常見問題。
source-git-commit: eb9bdcbd99d45afc913c5ade37e8fb5c62a3a456
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 2%

---


# SFTP服務升級 — 常見問題集

開啟 **2022年5月2日**,Adobe Analytics將升級其安全檔案傳輸通訊協定 [SFTP] 服務，以提高檔案傳輸的安全性。 經過此變更後，部分SFTP用戶端設定將不再受支援。 我們還將添加一些連接選項， **2022年3月1日**. 這只會影響使用SFTP傳送至Adobe Analytics或從Analytics擷取的資料。 FTP通訊協定將不會受到影響。 為避免服務中斷，請確定您的SFTP用戶端（程式碼、工具、服務）將符合下列詳細變更。

## 如何判斷我的組織目前使用的演算法、連線類型和通訊協定？

您使用的FTP/SFTP軟體應指出您設定用來與Adobe Analytics交換資料的連線中正使用哪些特定設定。 此軟體還應包含有關連接可用的不同選項的文檔。 此更新後將支援的選項在業界得到廣泛支援和接受。

## 哪些Adobe Analytics功能使用SFTP進行資料擷取？

下列功能提供使用SFTP將資料上傳至Adobe Analytics的選項。

* [分類](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html)

* [資料摘要](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datafeeds.html)

* [資料來源](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datasources.html)

* [Data Warehouse 傳遞的報表](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-dw-reports.html)

* 此外，有些自訂實作是透過 [工程服務](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-eng-services.html) 可使用SFTP來與Adobe交換資料。

## 此更新將包含哪些具體變更？

以下是將移除哪些連線和演算法以及將支援哪些演算法的詳細清單：

* SFTP協定mac算法：

   * 我們將不再支援：hmac-md5、hmac-md5-96、hmac-ripemd160、hmacripemd160@openssh.com、hmac-sha1、hmac-sha1-96、hmac-sha1-etm@openssh.com、umac-64-etm@openssh.com、umac-64@openssh.com

   * 我們只支援：hmac-sha2-512-etm@openssh.com、hmac-sha2-256-etm@openssh.com、umac-128-etm@openssh.com、hmac-sha2-512、hmacsha2-256、umac-128@openssh.com

* SFTP協定加密算法：

   * 我們將不再支援：3des-cbc、aes128-cbc、aes128-gcm@openssh.com、aes192-cbc、aes256-cbc、aes256-gcm@openssh.com、arcfour、arcfour128、arcfour256、blowfish-cbc、cast128-cbc、rijndael-cbc@lysator.liu.se

   * 我們只支援：aes128-ctr、aes192-ctr、aes256-ctr

* 支援的SFTP通訊協定連線：

   * 我們將不再支援使用scp和rsync命令或通過sftp協定的連接

   * 我們僅支援純SFTP通訊協定連線

* 支援的FTP/SFTP用戶端/通訊協定：

   * FTP:vsftpd版本3.0.2-25或更高版本

   * SFTP:openssh 7.4p1-21版或更高版本