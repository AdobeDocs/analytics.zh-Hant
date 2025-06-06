---
title: 分類匯入工具疑難排解
description: 使用分類匯入工具時的常見上傳問題。
feature: Classifications
exl-id: de3e9eca-9264-4711-b73a-4a1a3dd16715
source-git-commit: 04c626b1159be3e61569e462bf9d12957bd2a333
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 96%

---

# 分類匯入工具疑難排解

將分類資料上傳至 Adobe 時最常見的問題。

## 檔案格式或副檔名錯誤

分類需有特定檔案類型和格式才能成功上傳。如未正確儲存，系統會顯示錯誤訊息，且不會處理任何列。傳回的錯誤通常是&#x200B;*「第一欄必須是索引鍵」*，但可能是任何錯誤數量。務必勾選下列項目：

* **上傳試算表 (.xlsx)，而非 .tab 或 .txt 檔案**：當您以不正確的格式上傳分類檔案時，會收到錯誤訊息「*第一欄必須是索引鍵*」。分類匯入工具不知道如何處理 .xls 或 .xlsx 檔案。在 Excel 的「另存新檔」對話方塊中，設定正確的「另存新檔」類型：
   * 在 Windows 上，使用檔案格式 `Text (Tab delimited) (*.txt)`
   * 在 Mac 上，使用檔案格式 `Windows Formatted Text`。
* **在檔案儲存為活頁簿後變更副檔名**：嘗試直接重新命名副檔名會產生無效的活頁簿。請只使用 Excel 的「另存新檔」功能，或使用 Notepad++ 等文字編輯器編輯分類。
* **使用大寫副檔名**：大寫副檔名 (例如 `fileupload.TXT`) 無法正常發揮作用。請將副檔名重新命名為小寫 (`fileupload.txt`)。
* **不相符的字元編碼**：確保下載範本時，儲存的分類上傳編碼與原始編碼相符。如果您上傳原本以 UTF-8 編碼的 UTF-16 檔案，上傳會產生非預期的結果。Adobe 建議使用不含位元組順序標記的 UTF-8 上傳檔案。

## 檔案內容無效

若您上傳的檔案格式不正確，上傳工具會盡可能嘗試匯入更多有效的列。一些分類資料的常見問題：

* **已完成分類的列**：嘗試上傳已使用相同值分類的列時，匯入工具會傳回無效的列。這是可預期的結果，因為分類作業不會重新分類屬於相同分類的索引鍵值。此為通知而非錯誤。只要不變更匯出檔案內的所有列，其實不必擔心會發生任何問題。Adobe 建議僅上傳已變更的列。
* **標題與上傳的變數不符**：若您下載「追蹤程式碼」維度的分類範本，並嘗試將其上傳至 eVar 分類，上傳會失敗。請只使用符合匯出時之特定變數的匯出檔案。
* **索引鍵或分類值含有 0 值**：分類作業無法辨別 0 值與空白儲存格，因此無法為此值分類。如需詳細資訊，請參閱[分類匯入工具常見問題集](importer-faq.md)。
* **分類檔案包含逗號或特殊字元**：如需如何逸出值的詳細資訊，請參閱[分類匯入工具常見問題集](importer-faq.md)。
* **上傳檔案中的額外索引標籤**：編輯分類檔案時，有時會不小心置入額外的索引標籤。每一列的索引標籤數量相同，系統才能順利處理。若要檢查檔案中是否有額外索引標籤，請在純文字編輯器中反白標示所有文字，確保最後的列中沒有任何額外空格。
* **檔案中存在重複索引鍵值**：每個索引鍵值在每欄內都只能有一個分類。如果您嘗試多次分類相同的值，匯入工具會傳回錯誤。
* **存在子分類且設定不正確**：如果存在子分類，請查看以下項目：
   * 所有子分類值都會有父分類值
   * 不同子分類不會參照相同的父分類值
* **直欄不符**：如果任何指定列上有無效的直欄數，您會收到錯誤訊息「*行上的鍵有太多直欄*」。例如，您的分類上傳有 3 個欄位，而變數只有一個單項分類。請驗證您的上傳檔案，以確定欄位數不會大於為該變數設定的分類數。

## 疑難排解 FTP 匯入

下列是 FTP 分類無法處理已上傳檔案的常見原因：

* **遺失 .fin 檔案**：在桌面上建立空白文字文件，並將副檔名從 .txt 重新命名為 .fin。此 .fin 檔案的名稱必須符合相關分類檔案的名稱。舉例來說，如果您的 FTP 檔案名稱為 `fileupload.tab`，請將 .fin 檔案命名為 `fileupload.fin`。上傳 .fin 檔案後，兩個檔案都消失。
* **先上傳 .fin 檔案才上傳分類檔案**：有時會先建立 .fin 檔案，才將分類檔案上傳至 FTP 站台。檔案上傳順序不正確時，處理可能會失敗。移除兩個檔案後，先新增分類檔案，然後完全上傳分類檔案再上傳 .fin 檔案。
* **檔案大小過大**：Adobe 建議盡可能縮小分類檔案，以確保快速處理。
* **現有檔案已在處理中**：如果已為相同變數和報表套裝上傳多個檔案，舊檔案會停止處理，改用新檔案。如果使用多個檔案上傳分類，請待確認現有檔案已完成處理，再上傳新檔案。
* **上傳的檔案未置於根目錄中**：上傳至 Adobe FTP 站台的檔案必須置於根目錄中。如果分類匯入檔案置於子檔案夾中，系統不會擷取或處理這些檔案。

如果您上傳分類檔案時仍有問題，請聯絡 Adobe 客戶服務。
