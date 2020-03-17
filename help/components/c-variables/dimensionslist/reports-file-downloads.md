---
description: 檔案下載有助您瞭解訪客從網站下載檔案的頻率。檔案下載的內容可以是文字處理器文件、試算表、音訊檔、影片檔、使用者手冊等。其中包括直接從瀏覽器儲存與開啟的檔案，以及儲存至使用者電腦的檔案。此報告會顯示要下載之檔案的名稱，包括存取檔案所需的完整 URL 在內。
title: 檔案下載
topic: Reports
uuid: 897fc221-aa30-4eac-aca6-bccb76adaf71
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 檔案下載

檔案下載有助您瞭解訪客從網站下載檔案的頻率。檔案下載的內容可以是文字處理器文件、試算表、音訊檔、影片檔、使用者手冊等。其中包括直接從瀏覽器儲存與開啟的檔案，以及儲存至使用者電腦的檔案。此報告會顯示要下載之檔案的名稱，包括存取檔案所需的完整 URL 在內。

**導覽**

**[!UICONTROL 「報表]** > **[!UICONTROL 網站內容]** > **[!UICONTROL 連結]** > **[!UICONTROL 檔案下載」]**

若此報告未在預設位置中，請洽詢您的管理員，因為他們可能變更了預設功能表結構以因應您的組織獨特的需求。

使用此報告可以：

* 判斷從您網站中下載最頻繁的檔案。
* 瞭解是否在特定時段內某些檔案下載的次數更多。
* 驗證是否需要給定文件的所有格式。

   例如，您目前可能正將使用手冊翻譯為 12 種語言，且在您的網站上陸續發佈它們。透過檔案下載報告，您將可瞭解每個使用手冊版本的下載頻率，並且能評估是否有必要繼續將其翻譯為這 12 種語言。

**疑難排解**

行銷報告會從您的網站上任何包含 JavaScript 代碼的頁面中，擷取檔案下載的相關資訊。但必須要有特定變數存在並正確設定，才可報告檔案下載資訊。若此報告未顯示資料，或是未顯示預期值，請依照下列步驟驗證您的實作。

1. 在您的網站上，找出全域JavaScript 檔案。此檔案常命名為 [!DNL s_code.js]，但也可能已重新命名。如果已重新命名，您可以在網站上搜尋 JavaScript 檔案中的 *`s.account`* 值，該值是 JavaScript 程式碼的一部分。

1. 在此檔案中，找出 [s.trackDownloadLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_trackdownllinks.html) 變數。確定此變數設為 *true*。

1. 找出 [s.linkDownloadFileTypes](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkdownfiletypes.html) 變數。確定所有所需的副檔名都在這份清單中。如有必要，請在其中加入遺漏的副檔名，如 [!DNL .pdf]、[!DNL .zip] 等。

如果這些變數的設定正確，但是[!UICONTROL 檔案下載報告]還是沒有收到資料，您組織的受支援使用者應該聯絡客戶服務。
