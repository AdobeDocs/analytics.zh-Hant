---
description: 設定與 Adobe FTP 伺服器間安全傳輸的指示。
keywords: ftp;sftp
title: 使用 SFTP 連線至 Adobe FTP 帳戶
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
TQID: 'https://experienceleague.adobe.com/5X1Nx0V0hievpCe9G1Q6gJS1c55T3xl5FuneZxPx4TI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 214
ht-degree: 38%

---

# 使用SFTP連線至FTP帳戶

若要設定使用FTP的安全傳輸：

1. （視條件而定）如果您想要設定與Adobe FTP伺服器的安全傳輸：

   1. 請求Adobe託管的FTP帳戶（50 MB配額）。

   1. 建立公開/私密金鑰。

      * 在Linux環境中，執行：

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        如果您的原則不允許您使用ed25519，請執行：

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

        **注意：**&#x200B;這通常適用於在FIPS 186-4 (如ed25519下運作的客戶，在較新的FIPS 186-5中首先受到支援。

      * 在Windows環境中，使用puttyGen。

1. （視條件而定）如果您想要使用自己的FTP位置設定安全傳輸，您必須擁有包含有效RSA或ed25519公開金鑰的SFTP主機、使用者名稱和目的地站台。 建立摘要時，您可以下載相關的公開金鑰。

1. 建立名為 [!DNL `authorized_keys`] 的檔案 (無副檔名)。

1. 將公開金鑰的內容複製至 [!DNL `authorized_keys`]。

1. 上傳 [!DNL `authorized_keys`] 至 FTP 帳戶：

   * 連線至 Adobe FTP 帳戶。
   * 建立 [!DNL .ssh] 目錄 (如果尚未存在)。
   * 上傳 [!DNL `authorized_keys`] 檔案至 [!DNL .ssh] 目錄。

1. 使用 SFTP 登入該 FTP 帳戶以測試連線。

如需詳細資訊，請參閱[不使用密碼透過SFTP連線至Adobe](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)。

