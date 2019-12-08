---
description: Adobe支援將資料倉庫請求匯出至SFTP伺服器。
keywords: ftp;sftp
title: 傳送 Data Warehouse 請求至 SFTP 伺服器
uuid: 393634a1-0643-4d63-bb6e-fb80f1ba76c1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 傳送 Data Warehouse 請求至 SFTP 伺服器

Adobe支援將資料倉庫請求匯出至SFTP伺服器。

請確認下列工作已完成:

Adobe支援將資料倉庫請求匯出至SFTP伺服器，但必須符合下列條件：

* [!DNL sftp://] 通訊協定在主機欄位中指定(例如 [!DNL sftp://ftp.example.com])，且在請求「資料倉儲」報表時僅使用ONLY port 22。

   您也可以使用 [!DNL sftp+norename://] 選項，如下所述。

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

Alternatively, [!DNL sftp+norename://] can be specified instead of [!DNL sftp://] to upload the file directly with the final name, without a temporary [!DNL .part] file name during upload. 當SFTP伺服器在自動上傳期間處理檔案重新命名，而且上傳完成之前，檔案不可能處理時，此方法就適用。
