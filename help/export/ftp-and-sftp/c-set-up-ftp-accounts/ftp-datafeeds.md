---
description: 資料摘要是將 Adobe 收到的點按資料流資料匯出，可同時提供標準和自訂資料摘要。
keywords: ftp;sftp
title: 資料摘要
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
TQID: https://experienceleague.adobe.com/SWXC-g3KTGuKiT0CBFfptUSBigs8pgkPVdRLzWhl6z4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 30%

---

# 資料摘要

>[!NOTE]
>
>以下資訊與FTP和SFTP目的地型別有關。 FTP和SFTP是舊有的目的地型別。 設定資料摘要時，您應使用較安全的雲端目的地型別。 如需為資料摘要設定雲端目的地型別的詳細資訊，請參閱[建立資料摘要](/help/export/analytics-data-feed/create-feed.md)。

資料摘要是將 Adobe 收到的點按資料流資料匯出，可同時提供標準和自訂[資料摘要](/help/export/analytics-data-feed/data-feed-overview.md)。

如果您已購買 Adobe Data Warehouse，[!UICONTROL 標準資料摘要]您可以設定自己的 Analytics 資料摘要。 它們可以傳送到任何FTP帳戶（由Adobe設定或外部FTP的帳戶）。 Adobe 工程技術服務提供自訂的[!UICONTROL 資料摘要]，幾乎可透過所有方法進行傳送。

[!UICONTROL 資料摘要] FTP帳戶允許10GB （預設值）。 所有其他標準FTP帳戶預設為50MB。 當使用者端使用FTP帳戶作為適當預期用途時，某些高流量金額的使用者會快速填滿這些帳戶。 當FTP帳戶已滿時，無法將其他檔案推送至該帳戶。 因此，傳遞至該 FTP 帳戶的任何檔案 ([!UICONTROL 資料摘要]、資料倉庫請求等) 將停止傳遞。 這就是透過移除已接收和下載的檔案來管理Adobe FTP帳戶的重要原因之一。

當FTP帳戶已滿時，您應下載並移除目前的檔案，並通知Adobe空間已清除。 Adobe可以重新傳送尚未傳送的檔案。 有些工具（例如Data Warehouse）可讓使用者重新傳送這些檔案。 重新傳送可能不需要Adobe的參與。 如果您的FTP帳戶似乎經常有人填滿，請聯絡Adobe客戶服務，客戶服務提供替代傳送建議，包括增加帳戶的FTP空間與檔案編號配額。
