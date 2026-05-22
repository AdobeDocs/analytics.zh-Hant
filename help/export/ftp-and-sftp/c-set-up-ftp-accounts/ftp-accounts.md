---
description: 設定及使用 Adobe 代管的 FTP 帳戶。
keywords: ftp;sftp
title: 設定 FTP 帳戶 - 概觀
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
TQID: https://experienceleague.adobe.com/38oslnk-IS87YU9qpOJyEoqytnrMuK5lp3VtYnTyQOg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 6%

---

# 設定FTP或SFTP帳戶 — 概觀

設定及使用Adobe託管的FTP或SFTP帳戶。

Adobe維護高可用性、高效能FTP或SFTP叢集，這些叢集是專門為提高檔案傳輸可靠性而設計的，同時會持續確保高效能。

Adobe客戶會透過其標準流程收到維護通知，因為維護事件已排程。 為了確保Adobe FTP或SFTP系統如常運作並持續提供安全可靠的高效能資料傳輸，Adobe請您遵守下列准則：

* 在設定指定功能時，大部分的Adobe FTP或SFTP帳戶（分類、資料來源及其他）都會自動啟用。 對於資料摘要和一般檔案傳遞帳戶，Adobe客戶服務可為您設定新的FTP或SFTP帳戶。 此程式旨在確保FTP或SFTP帳戶的安全性和可用空間。
* 資料成功傳輸至使用者系統後，使用者應移除Adobe傳送至FTP或SFTP帳戶的資料。
* 不再需要FTP或SFTP帳戶時通知Adobe，以便將其停用。

Adobe FTP 主機名稱是 `ftp://ftp.omniture.com` 或 `ftp://ftp2.omniture.com`。

此項資訊以及使用者名稱和密碼應在CX Enterprise中提供（針對分類和資料來源），或由負責設定您申請之帳戶的Adobe代表提供。 如果您不知道要使用的FTP或SFTP位址，請聯絡您的Adobe客戶團隊，他們可提供正確位址。 此外，針對分類和資料來源帳戶，Adobe沒有處理FTP或SFTP檔案的特定時間。 相反地，Adobe會使用持續輪詢FTP或SFTP帳戶以尋找新檔案程式的指令碼。 系統會儘快處理上傳至這些帳戶的檔案。
