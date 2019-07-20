---
description: 設定與 Adobe FTP 伺服器間安全傳輸的指示。
keywords: ftp；sftp
seo-description: 設定與 Adobe FTP 伺服器間安全傳輸的指示。
seo-title: 使用SFTP連線至Adobe FTP帳戶
solution: Analytics
title: 使用SFTP連線至Adobe FTP帳戶
uuid: 4ff27b8-7276-3c68-87cb-35802b809e27
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 使用SFTP連線至Adobe FTP帳戶

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

1. 使用SFTP登入FTP帳戶來測試連線。

For more detailed information, see [How to Connect to Adobe via sFTP Without a Password_...](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846).
