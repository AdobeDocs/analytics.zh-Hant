---
description: Adobe FTP 政策針對連續 90 天無活動的 FTP 帳戶，會自動停用對該 FTP 帳戶的存取。
keywords: ftp;sftp
title: 刪除FTP和SFTP帳戶及資料
feature: FTP Export
exl-id: accf2f8d-c22c-4684-ba85-73a286325d0c
source-git-commit: 6008cd51b86e403668c15bbfb9d50513e46ddf4d
workflow-type: tm+mt
source-wordcount: '223'
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
