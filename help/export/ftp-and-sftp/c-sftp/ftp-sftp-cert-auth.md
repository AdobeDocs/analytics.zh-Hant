---
description: 若要不使用密碼連線至 FTP 帳戶，只能透過同時使用 SFTP 連線和替代驗證方法才能達成。 這需要用到稱為公開金鑰和私密金鑰的兩個檔案組合 (一個檔案存在 FTP 帳戶上，另一個檔案存在您的電腦上)。
keywords: ftp;sftp
title: 不使用密碼透過 SFTP 連線至 Adobe
feature: FTP Export
exl-id: 7ff9511c-50a2-466f-b5af-6bbd59941ce5
TQID: https://experienceleague.adobe.com/qQmzBUalqWjJ7FYow1DBCEfVixzultPI2PJSNhOsLlY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 609
ht-degree: 38%

---

# 不使用密碼透過 SFTP 連線至 Adobe

若要不使用密碼連線至 FTP 帳戶，只能透過同時使用 SFTP 連線和替代驗證方法才能達成。 這需要用到稱為公開金鑰和私密金鑰的兩個檔案組合 (一個檔案存在 FTP 帳戶上，另一個檔案存在您的電腦上)。

這並非比密碼驗證更不安全。 這是另一種驗證形式，不需要使用者每次都輸入密碼。 正確使用時，這些檔案可讓該特定電腦登入，而不需指定密碼。 這需要逐台電腦進行設定。 所有其他不使用這些金鑰檔案的連線仍需要指定密碼。

某些用戶端會要求使用 SFTP (安全檔案傳輸通訊協定) 來傳輸敏感資料。 SFTP 連線比一般 FTP 連線更安全，因為 SFTP 允許加密資料通訊。 依預設，所有 Adobe FTP 帳戶都可使用 SFTP。 您可經由在連接埠 22 上連線的 SFTP 用戶端，使用有效的使用者名稱和密碼來開啟 SFTP 連線 (不安全的一般 FTP 連線則使用連接埠 21)。

使用 SFTP 時，在特定條件下，可採用私密金鑰 (而不使用密碼) 連線至帳戶。 此方法可讓您的電腦使用金鑰檔進行驗證，而非一般的密碼驗證。 這表示只有擁有私密金鑰的電腦可以不使用密碼連線。 所有其他電腦/使用者仍需要使用密碼驗證（除非在這些其他電腦上也設定了私密金鑰）。

**若要設定並使用私密金鑰進行無密碼驗證**

1. 已建立FTP帳戶(Adobe)。

   Adobe代表可以建立FTP帳戶（如果尚未存在）。 請聯絡您的Adobe客戶團隊或Adobe客戶服務，以建立帳戶。
1. 公開/私密金鑰建立（客戶）。

   建立公開和私密金鑰組合。 私密金鑰是您電腦/伺服器的私密檔案，且位於該處。 公開金鑰檔案必須上傳至Adobe帳戶。 以這種方式使用時，您無需密碼驗證即可連線。 Adobe的公開金鑰檔案會與您電腦/伺服器上的私密金鑰檔案相符，並以該方式進行驗證。

   若要建立這些檔案，請洽詢您的內部網路支援團隊，建立適合您環境的金鑰組。 有許多工具和應用程式可用來建立這兩個檔案。

   以下顯示如何在UNIX Shell環境中執行此作業的範例。 這只是如何進行此作業的其中一例，並且可作為向團隊或內部網路群組溝通需求的有用參考點。

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

1. 將公開金鑰上傳至FTP帳戶（客戶）。

   上傳並測試公開金鑰。 連線至 Adobe FTP 帳戶並建立 [!DNL .ssh] 目錄 (如果尚未存在)。 上傳 [!DNL authorized_keys] 檔案至此 [!DNL .ssh] 目錄。 這可透過多種不同方式完成（命令列、圖形FTP使用者端等）。 您只需要建立目錄和上傳檔案的能力。

   這裡，再一次是使用UNIX shell執行此作業的範例。

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
