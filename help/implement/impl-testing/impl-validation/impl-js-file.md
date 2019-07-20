---
description: 請驗證 .JS 檔案是否正確參考自頁面。您可以指定相對於現行文件的路徑，也可以使用絕對路徑名稱。
keywords: Analytics 實施
seo-description: 請驗證 .JS 檔案是否正確參考自頁面。您可以指定相對於現行文件的路徑，也可以使用絕對路徑名稱。
seo-title: JavaScript JS檔案
solution: Analytics
title: JavaScript JS檔案
topic: 開發人員和實施
uuid: 6e83223f-2127-41d3-9806-bd085 fa2 a747
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# JavaScript JS檔案

請驗證 .JS 檔案是否正確參考自頁面。您可以指定相對於現行文件的路徑，也可以使用絕對路徑名稱。

```js
<script language="JavaScript" 
src="https://www.sampleco.com/javascript/includes/s_code.js"></script>
```

If some pages of the site are loaded in a secure protocol (https:), and reference the [!DNL AppMeasurement] for JavaScript file, ensure that the reference to the file is either secure (via https:) or code the reference as shown below. 此範例採用現行頁面的通訊協定，並防止「部分元素不安全」警告出現。

```js
<script language="JavaScript" 
src="//www.sampleco.com/javascript/includes/s_code.js"></script>
```

Ensure that the [!DNL .JS] file on the web servers have permissions appropriately set so that the file may be downloaded and executed by website visitors. If a different [!DNL .JS] file is used on development servers, set the "read only" attribute for the [!DNL .JS] file on production servers to avoid an overwrite. If altered, ensure that the following settings are set appropriately at the top of the [!DNL .JS] file:

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

If " *`s_account`*" is assigned a value at the top of the [!DNL .JS] file, ensure that the report suite ID (populated in the [!UICONTROL s_account]variable) is correct. Also ensure that the code in the page is not setting the [!UICONTROL Report Suite ID] ( *`s_account`* variable).

Examine the image request and variables to ensure that the "fallback method" (the third part of the "split" code in the example above) is not creating the image request instead of the [!DNL .JS] file. 「備援」方法只會以最少量的資訊建立影像要求，這可作為您的判斷依據。
