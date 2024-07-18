---
description: 設定及使用 Adobe 代管的 FTP 帳戶。
keywords: ftp;sftp
title: 設定 FTP 帳戶 - 概觀
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 92%

---

# 設定 FTP 帳戶 - 概觀

設定及使用 Adobe 代管的 FTP 帳戶。

Adobe 會維護高可用、高效能的 FTP 叢集，專門設計用來改善檔案傳輸可靠性，同時持續確保高效能。

當排定維護事件時，Adobe 客戶會透過標準程序收到維護通知。為了確保 Adobe FTP 系統如常運作並持續提供安全、可靠的高效能資料傳輸，Adobe 請您遵守以下準則：

* 設定了特定功能時，大部分 Adobe FTP 帳戶 (分類、資料來源及其他項目) 就會自動啟用。對於資料摘要和一般檔案傳遞帳戶，Adobe 客戶服務可為您設定新的 FTP 帳戶。此程序的設計目的，是為了同時確保 FTP 帳戶的安全性和可用空間。
* 當資料成功傳輸至使用者的系統後，使用者就應移除由 Adobe 傳遞至 FTP 帳戶的資料。
* 不再需要 FTP 帳戶時，請通知 Adobe 以將其停用。

Adobe FTP 主機名稱是 `ftp://ftp.omniture.com` 或 `ftp://ftp2.omniture.com`。

此項資訊以及使用者名稱和密碼應在 [!UICONTROL Experience Cloud] 中提供 (針對分類和資料來源)，或由負責設定您申請之帳戶的 Adobe 代表提供。如果您不知道要使用哪個FTP位址，請連絡您的Adobe客戶團隊，他們可提供正確的位址。 此外，對於分類和資料來源帳戶，Adobe 不是在一天的某個固定時段處理 FTP 檔案。Adobe 是使用指令檔，時常輪詢 FTP 帳戶來處理新的檔案。上傳至這些帳戶的檔案都會盡快處理。
