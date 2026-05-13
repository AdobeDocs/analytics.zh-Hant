---
description: Adobe FTP 政策針對連續 90 天無活動的 FTP 帳戶，會自動停用對該 FTP 帳戶的存取。
keywords: ftp;sftp
title: 刪除FTP和SFTP帳戶及資料
feature: FTP Export
exl-id: accf2f8d-c22c-4684-ba85-73a286325d0c
TQID: https://experienceleague.adobe.com/7x8bYAZmZ4Bn-7Sbpf7wGFfOQbkxRQ2CsUcXUgVDTPQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 237
ht-degree: 8%

---

# 刪除FTP和SFTP帳戶及資料

Adobe FTP和SFTP原則可能會停用連續90天無活動的FTP和SFTP帳戶存取權。

Adobe在額外的90天寬限期後，可能會移除已停用的FTP和SFTP帳戶（並永久移除這些帳戶中儲存的所有資料）。 例如，閒置達90天（從2025年7月5日到2025年10月2日）的SFTP帳戶已於2025年10月3日停用。 接著在2026年1月2日完全移除。

2025年10月5日之前不會停用任何帳戶，且2026年1月2日之前不會移除任何帳戶。

如果已有90天未存取作用中帳戶的舊資料，Adobe也可能會永久移除這些資料。

為了協助我們進行此程式，並確保FTP或SFTP環境持續為客戶提供安全可靠的資料傳輸，我們請客戶執行下列作業：

* 成功將傳出資料傳輸至您的內部環境後，從FTP和SFTP系統移除這些資料。 Adobe可能會在90天後識別並移除系統中剩餘的任何檔案。
* 當不再需要使用FTP和SFTP帳戶時，通知Adobe以便停用和移除它們。
