---
description: Adobe 支援將 Data Warehouse 請求匯出至 SFTP 伺服器。
keywords: ftp;sftp
title: 傳送 Data Warehouse 請求至 SFTP 伺服器
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
source-git-commit: d8bfad5d388f906c7c7301a9126813f5c2a5dbaa
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 59%

---

# 傳送 Data Warehouse 請求至 SFTP 伺服器

Adobe支援將Data Warehouse請求匯出至SFTP伺服器，如所述 [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) 在文章中， [設定Data Warehouse請求的報表目的地](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).

請確認下列工作已完成：

* 請求Data Warehouse報告時只使用連線埠22。
* 在您用來登入之使用者身分的根目錄下，Adobe 的 `.ssh` 檔案位於 `authorized_keys` 目錄中.
* 目的地不是 `ftp.omniture.com`。不支援在 Adobe 內部伺服器之間使用 SFTP 通訊協定。
* 目的地支援單因素 (PKI) 驗證。如果有雙因素問題，報表傳遞會失敗。請勿將您的伺服器設定為使用雙因素驗證。Adobe Analytics 要求在登入中只能使用金鑰，不能有其他項目。
* Adobe 支援 SSHv2 加密，並可回復為 SSHv1 (僅限 RSA 金鑰)。

若想透過 SFTP 成功傳送 Data Warehouse 請求：

1. 完成中所述的步驟 [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) 在文章中， [設定Data Warehouse請求的報表目的地](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)，包括下載公開金鑰。
1. 使用用於Data Warehouse請求的相同認證登入SFTP網站。
1. 在根目錄瀏覽至名為 `.ssh` 的資料夾 (如果該資料夾不存在，請建立一個)，然後將 `authorized_keys` 檔案置於該處。

1. 完成Data Warehouse要求（如果尚未完成），如所述 [設定Data Warehouse請求的報表目的地](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).
