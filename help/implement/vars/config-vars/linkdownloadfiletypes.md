---
title: linkDownloadFileTypes
description: 判斷要以下載連結形式自動追蹤的副檔名。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkDownloadFileTypes

When [`trackDownloadLinks`](trackdownloadlinks.md) is enabled and a visitor clicks on a link, AppMeasurement checks the URL of the link for filetype extensions. 如果連結 URL 包含 `linkDownloadFileTypes` 中的檔案類型，系統會自動傳送下載連結影像要求。

使用 `linkDownloadFileTypes` 來自訂您要將哪些副檔名計為下載連結。

>[!NOTE] 系統只會自動追蹤實際點按，不會自動追蹤以下類型的連結：
>
> * 在頁面載入時自動開始的檔案下載
> * 在重新導向後觸發的下載
> * 按一下右鍵並選擇「另存目標...」
> * 使用 JavaScript 的連結，如 `javascript:openLink()`
>
> 
For these download types, you can manually call the [`tl()`](../functions/tl-method.md) method.

如果點按的連結符合退出連結和下載連結兩條件，下載連結類型的優先較高。

## Adobe Experience Platform Launch 中的下載擴充功能

Download Extensions is a list of file extensions with a field to add more under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. 展開accordion [!UICONTROL Link Tracking] ，以顯示欄 [!UICONTROL Download Extensions] 位。

Add file extensions to the list by entering text in the field and clicking [!UICONTROL Add]. 按一下各自的「X」圖示，從清單中移除副檔名。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.linkDownloadFileTypes

`s.linkDownloadFileTypes` 變數是以逗號分隔的副檔名字串，因此請勿使用空格。

如果此變數未定義，自動下載連結追蹤將無法發揮作用 (即便 [`trackDownloadLinks`](trackdownloadlinks.md) 是 `true`)。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
