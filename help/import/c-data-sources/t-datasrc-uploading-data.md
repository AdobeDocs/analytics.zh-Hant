---
description: 上傳資料來源檔案的步驟。
seo-description: 上傳資料來源檔案的步驟。
seo-title: 上傳Data Sources檔案
solution: Analytics
subtopic: 資料來源
title: 上傳Data Sources檔案
topic: 開發人員和實施
uuid: 5a9dde91-1297-47e5-9393-611b40413c17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 上傳Data Sources檔案

上傳資料來源檔案的步驟。

準備好資料來源的資料檔案後，將其提交給資料來源處理。Adobe 維護數個資料來源 FTP 伺服器，您可以將資料來源檔案上傳到這些位置。關於資料來源 FTP 伺服器，請記住:

* 在「[!UICONTROL 資料來源管理]」標籤中，選取資料來源項目旁的 FTP 資訊，可查看資料來源的 FTP 帳戶的 FTP 主機、登入及密碼資訊。任何可以存取該資訊的使用者都可以將資料上傳到您的報表套裝。
* 出於安全考慮，FTP 帳戶閒置 30 天之後會被關閉。
* FTP 帳戶專屬於「資料來源」所有。您不能使用一個 FTP 帳戶上傳資料來源檔案到多個資料來源。

**上傳資料來源檔案**

1. 使用 FTP 用戶端將資料傳送至您的資料來源 FTP 網站。

   (「資料來源管理員」中的 FTP 資訊連結)。

1. Upload a [!DNL .fin] file to notify Adobe that the Data Sources file upload is complete.

   [!DNL .fin] 檔案的名稱必須與Data Sources檔案完全相同，但副檔名除外。Adobe does not queue the Data Sources file for processing until you upload the [!DNL .fin] file.

   請等到所有資料來源檔案完成上傳後，才上傳檔案。否則，資料來源可能會嘗試處理不完整的檔案。
1. 在資料來源檔案處理期間，請留意任何出現的訊息。

   「資料來源管理員」會顯示檔案處理期間發生的任何錯誤。

