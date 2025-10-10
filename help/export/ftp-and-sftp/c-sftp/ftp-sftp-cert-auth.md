---
description: 若要不使用密碼連線至 FTP 帳戶，只能透過同時使用 SFTP 連線和替代驗證方法才能達成。這需要用到稱為公開金鑰和私密金鑰的兩個檔案組合 (一個檔案存在 FTP 帳戶上，另一個檔案存在您的電腦上)。
keywords: ftp;sftp
title: 不使用密碼透過 SFTP 連線至 Adobe
feature: FTP Export
exl-id: 7ff9511c-50a2-466f-b5af-6bbd59941ce5
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 97%

---

# 不使用密碼透過 SFTP 連線至 Adobe

若要不使用密碼連線至 FTP 帳戶，只能透過同時使用 SFTP 連線和替代驗證方法才能達成。這需要用到稱為公開金鑰和私密金鑰的兩個檔案組合 (一個檔案存在 FTP 帳戶上，另一個檔案存在您的電腦上)。

此方法不會比密碼驗證更不安全。這是不需要使用者每次都輸入密碼的另一種驗證形式。如果使用正確，這些檔案可讓該部特定電腦不須指定密碼即可登入。這需要在每一部電腦上逐一進行設定。未使用金鑰檔案的其他所有電腦仍需指定密碼。

某些用戶端會要求使用 SFTP (安全檔案傳輸通訊協定) 來傳輸敏感資料。SFTP 連線比一般 FTP 連線更安全，因為 SFTP 允許加密資料通訊。依預設，所有 Adobe FTP 帳戶都可使用 SFTP。您可經由在連接埠 22 上連線的 SFTP 用戶端，使用有效的使用者名稱和密碼來開啟 SFTP 連線 (不安全的一般 FTP 連線則使用連接埠 21)。

使用 SFTP 時，在特定條件下，可採用私密金鑰 (而不使用密碼) 連線至帳戶。此方法可讓您的電腦使用金鑰檔案來驗證，以取代平常使用的密碼驗證。這表示只有持有私密金鑰的電腦才能不使用密碼連線。所有其他電腦/使用者仍需使用密碼驗證 (除非也已在這些電腦上設定好私密金鑰)。

**若要設定並使用私密金鑰來進行無密碼驗證**

1. 已建立 FTP 帳戶 (Adobe)。

   如果還沒有 FTP 帳戶，可由 Adobe 代表為您建立 FTP 帳戶。請聯絡您的Adobe客戶團隊或Adobe客戶服務，以建立帳戶。
1. 建立公開/私密金鑰 (客戶)。

   建立公開和私密金鑰組合。私密金鑰是存在於您的電腦/伺服器上，並由其專用的檔案。公開金鑰檔案則必須上傳至 Adobe 帳戶。使用這種方式時，您可不用密碼驗證而連線。Adobe 上的公開金鑰檔案會與您電腦/伺服器上的私密金鑰進行比對，透過此方式加以驗證。

   若要建立這些檔案，請聯繫您的內部網路支援小組，建立適用於您環境的金鑰集。有許多工具和應用程式可用來建立這兩個檔案。

   以下顯示如何在 UNIX 殼層環境中完成此項作業的範例。這只是示範完成此項作業的範例，以供做為您與您的團隊或內部網路小組溝通的一個有用參考點。

   ```
   // Linux/Unix (bash shell)
   
   // First make sure the ".ssh" directory exists
   
   $ mkdir ~/.ssh
   
   $ cd ~/.ssh
   
   // Now actually generate the key pair
   
   // Usually we will want to create an empty passphrase (just hit "Enter" for both password prompts)
   
   $ ssh-keygen -q -t dsa
   
   Enter file in which to save the key (/home/user/.ssh/id_dsa):
   
   Enter passphrase (empty for no passphrase): ...
   
   Enter same passphrase again: ...
   
   // Rename or copy the public key file to "authorized_keys"
   
   // This "authorized_keys" file is the one that we will upload to the Adobe FTP server in step 3
   
   $ cp id_dsa.pub authorized_keys 
   ```

1. 上傳公開金鑰至 FTP 帳戶 (客戶)。

   上傳並測試公開金鑰。連線至 Adobe FTP 帳戶並建立 [!DNL .ssh] 目錄 (如果尚未存在)。上傳 [!DNL authorized_keys] 檔案至此 [!DNL .ssh] 目錄。有許多方法可以完成此項作業 (命令列、圖形 FTP 用戶端等等)。您只需具備建立目錄和上傳檔案的能力即可。

   以下是使用 UNIX 殼層完成此項作業的範例。

   ```
   $ ftp ftp.Adobe.com
   
   OR (depending on hostname provided by Adobe)
   
   $ ftp ftp2.Adobe.com
   
   // Enter username and password for account as prompted
   
   ftp> mkdir .ssh
   
   ftp> cd .ssh
   
   ftp> put authorized_keys
   
   ftp> exit
   
   // Now test the connection by logging in to the server using "sftp" command:
   
   $ sftp username@ftp.omniture.com
   
   OR (depending on hostname provided by Adobe)
   
   $ sftp username@ftp2.omniture.com
   
   // You should immediately receive an sftp prompt without having to enter the password:
   
   sftp>
   ```
