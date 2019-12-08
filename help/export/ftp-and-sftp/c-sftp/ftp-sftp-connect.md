---
description: 設定與 Adobe FTP 伺服器間安全傳輸的指示。
keywords: ftp;sftp
title: 使用 SFTP 連線至 Adobe FTP 帳戶
uuid: 4faf27b8-7276-4c68-87cb-35802b809e27
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用 SFTP 連線至 Adobe FTP 帳戶

設定與 Adobe FTP 伺服器間安全傳輸的指示。

1. 申請 Adobe 託管的 FTP 帳戶 (50 MB 配額)。
1. 建立公開/私密 RSA 金鑰。在 Linux 中，執行:

   ```
   ssh-keygen -t rsa
   ```

   如果是在 Windows 環境，請使用 puttyGen 建立金鑰。

1. Create a file named [!DNL authorized_keys] (no extension).
1. Copy the contents of the Public key into [!DNL authorized_keys].
1. Upload [!DNL authorized_keys] to an FTP account:

   * 連線至 Adobe FTP 帳戶。
   * Create a [!DNL .ssh] directory (if it does not already exist).
   * Upload the [!DNL authorized_keys] file to the [!DNL .ssh] directory.

1. 使用SFTP登入FTP帳戶以測試連線。

[如需詳細資訊，請 ](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)參閱如何透過sFTP不使用密碼連線至Adobe_....
