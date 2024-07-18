---
description: 設定與 Adobe FTP 伺服器間安全傳輸的指示。
keywords: ftp;sftp
title: 使用 SFTP 連線至 Adobe FTP 帳戶
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 62132284ca70f3bdb1a8896e4548b8b63a5c03c8
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 58%

---

# 使用SFTP連線至FTP帳戶

若要設定使用FTP的安全傳輸：

1. （視條件而定）如果您想要設定與Adobe FTP伺服器的安全傳輸：

   1. 申請 Adobe 託管的 FTP 帳戶 (50 MB 配額)。

   1. 建立公開/私人RSA金鑰。

      * 在Linux環境中，執行：

        ```
        ssh-keygen -t rsa
        ```

      * 在Windows環境中，使用puttyGen。

1. （視條件而定）如果您想使用自己的FTP位置設定安全傳輸，您必須擁有包含有效RSA或DSA公開金鑰的SFTP主機、使用者名稱和目的地站台。 建立摘要時，您可以下載相關的公開金鑰。

1. 建立名為 [!DNL authorized_keys] 的檔案 (無副檔名)。

1. 將公開金鑰的內容複製至 [!DNL authorized_keys]。

1. 上傳 [!DNL authorized_keys] 至 FTP 帳戶：

   * 連線至 Adobe FTP 帳戶。
   * 建立 [!DNL .ssh] 目錄 (如果尚未存在)。
   * 上傳 [!DNL authorized_keys] 檔案至 [!DNL .ssh] 目錄。

1. 使用 SFTP 登入該 FTP 帳戶以測試連線。

如需詳細資訊，請參閱[如何透過 SFTP 而不使用密碼連線至 Adobe](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)。
