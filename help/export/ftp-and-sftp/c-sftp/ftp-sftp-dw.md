---
description: Adobe支援將Data Warehouse請求匯出至SFTP伺服器。
keywords: ftp；sftp
seo-description: Adobe支援將Data Warehouse請求匯出至SFTP伺服器。
seo-title: 傳送資料倉庫請求至SFTP伺服器
solution: Analytics
title: 傳送資料倉庫請求至SFTP伺服器
uuid: 393634a1-0643-4d63-bb6 e-fb80 f1 ba76 c1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 傳送資料倉庫請求至SFTP伺服器

Adobe支援將Data Warehouse請求匯出至SFTP伺服器。

請確認下列工作已完成:

如果符合下列條件，Adobe支援將Data Warehouse請求匯出至SFTP伺服器：

* [!DNL sftp://] 通訊協定是在主機欄位中指定(例如， [!DNL sftp://ftp.example.com])，而只有連接埠22才會在請求「資料倉儲」報表時使用。

   You can also use the [!DNL sftp+norename://] option, as described below.

* Adobe's [!DNL authorized_keys] file is in the [!DNL .ssh] directory within the root directory of the user you log in with

* 目的地不是 [!DNL ftp.omniture.com]。不支援在 Adobe 內部伺服器之間使用 SFTP 通訊協定。
* 目的地支援單因素 (PKI) 驗證。如果有雙因素問題，報表傳遞會失敗。請勿將您的伺服器設定為使用雙因素驗證。Adobe Analytics 要求在登入中只能使用金鑰，不能有其他項目。
* Adobe 支援 SSHv2 加密，並可回復為 SSHv1 (僅限 RSA 金鑰)。

To successfully send a [!DNL Data Warehouse] request via SFTP:

1. 請貴組織的受支援使用者聯絡客戶服務，取得 [!DNL authorized_keys] 檔案。
1. After this file is obtained, log in to the FTP site under the same credentials that are used for the [!DNL Data Warehouse] request.
1. In the root directory, navigate to the folder named [!DNL .ssh] (if one does not exist, create one) and place the [!DNL authorized_keys] file there.

1. Go to the [!DNL Data Warehouse] request manager. Configure the request as desired, then click **[!UICONTROL Advanced Delivery Options]**.

1. In the pop-up window, click **[!UICONTROL FTP]**, then specify the ftp site (including the [!DNL sftp://] protocol, such as [!DNL sftp://ftp.omniture.com]) via port 22.

   Including the [!DNL sftp://] protocol is only permitted when using SFTP. Regular FTP requests should omit the protocol prefix (such as, [!DNL ftp.omniture.com] instead of [!DNL ftp://ftp.omniture.com]).

1. 在「資料夾」欄位中輸入您要放置檔案的資料夾名稱。資料夾是必填欄位。
1. 輸入在步驟 2 中使用的相同使用者名稱和密碼。
1. Click **[!UICONTROL Send]**.

sftp PUT 命令會在指定的目錄中放置一個副檔名為 .part 的暫存檔。上傳完成後，該檔案的副檔名會重新命名為最終副檔名，此時即代表該檔案已可供您使用。

Alternatively, [!DNL sftp+norename://] can be specified instead of [!DNL sftp://] to upload the file directly with the final name, without a temporary [!DNL .part] file name during upload. 當SFTP伺服器在自動上傳期間處理檔案重新命名時，此方法即適用，而且在上傳完成之前，也不可能處理檔案。
