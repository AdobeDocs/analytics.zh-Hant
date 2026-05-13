---
description: Adobe 支援將 Data Warehouse 請求匯出至 SFTP 伺服器。
keywords: ftp;sftp
title: 傳送 Data Warehouse 請求至 SFTP 伺服器
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
TQID: https://experienceleague.adobe.com/nBerOKEbILwAK5OyayVgdBPN8vq24kk-DXY6XMT50wg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 258
ht-degree: 31%

---

# 傳送 Data Warehouse 請求至 SFTP 伺服器

Adobe支援將Data Warehouse請求匯出至SFTP伺服器，如[SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp)文章[設定Data Warehouse請求的報表目的地](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)中所述。

請確認下列工作已完成：

* 請求Data Warehouse報表時只使用連線埠22。
* Adobe的`authorized_keys`檔案位於您用來登入之使用者根目錄內的`.ssh`目錄中。
* 目的地不是 `ftp.omniture.com`。 不支援Adobe內部伺服器之間的SFTP通訊協定。
* 目的地支援單因素(PKI)驗證。 如果存在雙因素挑戰，報表傳送將會失敗。 請勿將您的伺服器設定為使用雙因素驗證。 Adobe Analytics要求僅使用金鑰登入，不使用任何其他專案。
* Adobe支援SSHv2加密，並退回至SSHv1 （僅限RSA金鑰）。

若想透過 SFTP 成功傳送 Data Warehouse 請求：

1. 完成文章[設定Data Warehouse要求的報表目的地](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)中[SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp)所述的步驟，包括下載公開金鑰。
1. 使用用於Data Warehouse請求的相同認證登入SFTP網站。
1. 在根目錄瀏覽至名為 `.ssh` 的資料夾 (如果該資料夾不存在，請建立一個)，然後將 `authorized_keys` 檔案置於該處。

1. 如果您尚未完成Data Warehouse要求，請依照[設定Data Warehouse要求的報表目的地](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)中的說明完成。
