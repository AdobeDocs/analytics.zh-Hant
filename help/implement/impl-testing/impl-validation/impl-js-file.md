---
description: 請驗證 .JS 檔案是否正確參考自頁面。您可以指定相對於現行文件的路徑，也可以使用絕對路徑名稱。
keywords: Analytics 實作
seo-description: 請驗證 .JS 檔案是否正確參考自頁面。您可以指定相對於現行文件的路徑，也可以使用絕對路徑名稱。
seo-title: JavaScript JS 檔案
solution: Analytics
title: JavaScript JS 檔案
topic: 開發人員和實作
uuid: 6e83223f-2127-41d3-9806-bd085fa2a747
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# JavaScript JS 檔案

請驗證 .JS 檔案是否正確參考自頁面。您可以指定相對於現行文件的路徑，也可以使用絕對路徑名稱。

```js
<script language="JavaScript" 
src="https://www.sampleco.com/javascript/includes/s_code.js"></script>
```

若網站的部分頁面是以安全通訊協定 (https:) 載入的，並且參考 JavaScript 適用的 [!DNL AppMeasurement] 檔案，請確定對於該檔案的參考是安全的 (透過 https:)，或以下列方式為參考編碼。此範例採用現行頁面的通訊協定，並防止「部分元素不安全」警告出現。

```js
<script language="JavaScript" 
src="//www.sampleco.com/javascript/includes/s_code.js"></script>
```

請確定 Web 伺服器上的 [!DNL .JS] 檔案已適當設定權限，讓檔案可供網站訪客下載及執行。若在開發伺服器上使用不同的 [!DNL .JS] 檔案，請為生產伺服器上的 [!DNL .JS] 檔案設定「唯讀」屬性，以避免覆寫。若有所更改，請在 [!DNL .JS] 檔案頂端確認下列設定已適當設定:

```js
/************************** CONFIG SECTION **************************/
/* You may add or alter any code config here.                       */
/* Link Tracking Config */
s.trackDownloadLinks=false /* true for download tracking */
s.trackExternalLinks=false /* true for exit link tracking */
s.trackInlineStats=false /* true for ClickMap support */
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls"
s.linkInternalFilters="javascript:"
s.linkLeaveQueryString=false
s.linkTrackVars="None" 
s.linkTrackEvents="None"
```

若「*`s_account`*」在 [!DNL .JS] 檔案頂端已有指派值，請確定報表套裝 ID (已在 [!UICONTROL s_account] 變數中填入) 正確無誤。同時也請確定頁面中的程式碼未設定[!UICONTROL 報表套裝 ID ](*`s_account`* 變數)。

請檢查影像要求與變數，以確定「備援方法」(上述範例中，「分割」程式碼的第三個部分) 未建立影像要求，而不是 [!DNL .JS] 檔案。「備援」方法只會以最少量的資訊建立影像要求，這可作為您的判斷依據。
