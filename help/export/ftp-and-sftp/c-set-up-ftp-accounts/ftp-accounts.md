---
description: 設定和使用 Adobe 託管的 FTP 帳戶。
keywords: ftp;sftp
title: 設定 FTP 帳戶 - 概觀
uuid: e5524619-248a-4aae-9f64-cd7d33f3c407
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 設定 FTP 帳戶 - 概觀

設定和使用 Adobe 託管的 FTP 帳戶。

Adobe 會維護高可用、高效能的 FTP 叢集，專門設計用來改善檔案傳輸可靠性，同時持續確保高效能。

當排定維護事件時，Adobe 客戶會透過標準程序收到維護通知。為了確保 Adobe FTP 系統如常運作並持續提供安全、可靠的高效能資料傳輸，Adobe 請您遵守以下準則:

* 設定了特定功能時，大部分 Adobe FTP 帳戶 (分類、資料來源及其他項目) 就會自動啟用。對於資料饋送和一般檔案傳遞帳戶，Adobe 客戶服務可為您設定新的 FTP 帳戶。此程序的設計目的，是為了同時確保 FTP 帳戶的安全性和可用空間。
* 當資料成功傳輸至使用者的系統後，使用者就應移除由 Adobe 傳遞至 FTP 帳戶的資料。
* 不再需要 FTP 帳戶時，請通知 Adobe 以將其停用。

The Adobe FTP host name is [!DNL ftp.omniture.com] or [!DNL ftp2.omniture.com].

This information, along with a username and password, should be provided either within the [!UICONTROL Experience Cloud] (for classifications and Data Sources), or by the Adobe representative responsible for setting up the account at your request. 如果不清楚該使用哪個 FTP 位址，請聯絡您的 Adobe 客戶經理，他會提供正確位址給您。此外，對於分類和資料來源帳戶，Adobe 不是在一天的某個固定時段處理 FTP 檔案。Adobe 是使用指令檔，時常輪詢 FTP 帳戶來處理新的檔案。上傳至這些帳戶的檔案都會盡快處理。
