---
title: linkDownloadFileTypes
description: 判斷要以下載連結形式自動追蹤的副檔名。
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
source-git-commit: 49bf0a459a096e011ff60724aa5bee4fb7721a21
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 100%

---

# linkDownloadFileTypes

當 [`trackDownloadLinks`](trackdownloadlinks.md) 啟用且訪客點按連結時，AppMeasurement 會檢查連結的 URL，取得檔案類型副檔名。如果連結 URL 包含 `linkDownloadFileTypes` 中的檔案類型，系統會自動傳送下載連結影像要求。

使用 `linkDownloadFileTypes` 來自訂您要將哪些副檔名計為下載連結。

>[!NOTE]
>
>系統只會自動追蹤實際點擊， 不會自動追蹤以下類型的連結：
>
>* 在頁面載入時自動開始的檔案下載
>* 在重新導向後觸發的下載
>* 按一下右鍵並選擇「另存目標...」
>* 使用 JavaScript 的連結，如 `javascript:openLink()`

>
>對於這些下載類型，您可以手動呼叫 [`tl()`](../functions/tl-method.md) 方法。

如果點擊的連結符合退出連結和下載連結這兩個條件，則下載連結類型優先。

## 使用 Adobe Experience Platform 中的標記下載擴充功能

「下載擴充功能」是副檔名清單，其中包含的欄位可在設定 Adobe Analytics 擴充功能時，於「[!UICONTROL 連結追蹤]」摺疊式功能表下方新增更多副檔名。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「連結追蹤」]摺疊式功能表，如此可顯示[!UICONTROL 「下載擴充功能」]欄位。

在欄位中輸入文字並按一下[!UICONTROL 「新增」]，將副檔名新增至清單。按一下各個項目的「X」圖示，可將副檔名從清單中移除。

## AppMeasurement 和自訂程式碼編輯器中的 s.linkDownloadFileTypes

`s.linkDownloadFileTypes` 變數是以逗號分隔的副檔名字串，因此請勿使用空格。

如果此變數未定義，自動下載連結追蹤將無法發揮作用 (即便 [`trackDownloadLinks`](trackdownloadlinks.md) 是 `true`)。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
