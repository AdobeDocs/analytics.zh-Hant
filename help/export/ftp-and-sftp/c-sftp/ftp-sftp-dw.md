---
description: Adobe 支援將 Data Warehouse 請求匯出至 SFTP 伺服器。
keywords: ftp;sftp
title: 傳送 Data Warehouse 請求至 SFTP 伺服器
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: ht
source-wordcount: '421'
ht-degree: 100%

---

# 傳送 Data Warehouse 請求至 SFTP 伺服器

Adobe 支援將 Data Warehouse 請求匯出至 SFTP 伺服器。

請確認下列工作已完成：

符合下列條件時，Adobe 支援將 Data Warehouse 請求匯出至 SFTP 伺服器：

* 在主機欄位中指定 `sftp://` 通訊協定 (例如 `sftp://ftp.example.com`)，並只使用連接埠 22 來請求 Data Warehouse 報表。您也可以使用 `sftp+norename://` 選項，如下所述。
* 在您用來登入之使用者身分的根目錄下，Adobe 的 `.ssh` 檔案位於 `authorized_keys` 目錄中
* 目的地不是 `ftp.omniture.com`。不支援在 Adobe 內部伺服器之間使用 SFTP 通訊協定。
* 目的地支援單因素 (PKI) 驗證。如果有雙因素問題，報表傳遞會失敗。請勿將您的伺服器設定為使用雙因素驗證。Adobe Analytics 要求在登入中只能使用金鑰，不能有其他項目。
* Adobe 支援 SSHv2 加密，並可回復為 SSHv1 (僅限 RSA 金鑰)。

若想透過 SFTP 成功傳送 Data Warehouse 請求：

1. 請貴組織的受支援使用者聯絡客戶服務，取得 `authorized_keys` 檔案。
1. 取得該檔案後，使用用於 Data Warehouse 請求的相同認證登入 FTP 網站。
1. 在根目錄瀏覽至名為 `.ssh` 的資料夾 (如果該資料夾不存在，請建立一個)，然後將 `authorized_keys` 檔案置於該處。

1. 前往 Data Warehouse 請求管理員。視需要設定請求，然後按一下「**[!UICONTROL 進階傳送選項]**」。

1. 在快顯視窗中按一下&#x200B;**[!UICONTROL 「FTP」]**，接著指定 FTP 網站 (包括 `sftp://` 通訊協定，例如 `sftp://ftp.omniture.com`) 經由連接埠 22。

   只有使用 SFTP 時才允許加入 `sftp://` 通訊協定。一般 FTP 請求應該忽略通訊協定首碼 (例如 `ftp.omniture.com`，而非 `ftp://ftp.omniture.com`)。

1. 在「資料夾」欄位中輸入您要放置檔案的資料夾名稱。資料夾是必填欄位。
1. 輸入在步驟 2 中使用的相同使用者名稱和密碼。
1. 按一下「**[!UICONTROL 傳送]**」。

sftp PUT 命令會在指定的目錄中放置一個副檔名為 .part 的暫存檔。上傳完成後，該檔案的副檔名會重新命名為最終副檔名，此時即代表該檔案已可供您使用。

可以指定 `sftp+norename://` 而不是 `sftp://` 以直接上傳具有最終名稱的檔案，不必在上傳期間使用暫時性的 `.part` 檔案名稱。SFTP 伺服器在上傳期間自動處理檔案重新命名時，此方法即適用，而且在上傳完成之前也不可能處理檔案。
