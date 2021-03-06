---
description: 設定與 Adobe FTP 伺服器間安全傳輸的指示。
keywords: ftp;sftp
title: 使用 SFTP 連線至 Adobe FTP 帳戶
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: ht
source-wordcount: '134'
ht-degree: 100%

---

# 使用 SFTP 連線至 Adobe FTP 帳戶

設定與 Adobe FTP 伺服器間安全傳輸的指示。

1. 申請 Adobe 託管的 FTP 帳戶 (50 MB 配額)。
1. 建立公開/私密 RSA 金鑰。在 Linux 中，執行：

   ```
   ssh-keygen -t rsa
   ```

   如果是在 Windows 環境，請使用 puttyGen 建立金鑰。

1. 建立名為 [!DNL authorized_keys] 的檔案 (無副檔名)。
1. 將公開金鑰的內容複製至 [!DNL authorized_keys]。
1. 上傳 [!DNL authorized_keys] 至 FTP 帳戶：

   * 連線至 Adobe FTP 帳戶。
   * 建立 [!DNL .ssh] 目錄 (如果尚未存在)。
   * 上傳 [!DNL authorized_keys] 檔案至 [!DNL .ssh] 目錄。

1. 使用 SFTP 登入該 FTP 帳戶以測試連線。

如需詳細資訊，請參閱[如何透過 SFTP 而不使用密碼連線至 Adobe](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)。
