---
title: linkDownloadFileTypes
description: 判斷會自動被追蹤為下載連結的副檔名。
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkDownloadFileTypes

當訪 `trackDownloadLinks` 客點按連 `true` 結時，AppMeasurement會檢查連結的URL，以取得檔案類型副檔名。 如果連結URL包含中找到的檔案類型， `linkDownloadFileTypes`則會自動傳送下載連結影像要求。

使用 `linkDownloadFileTypes` 來自訂您要計為下載連結的副檔名。

> [!NOTE] 只會自動追蹤實際的點按次數。 不會自動追蹤下列類型的連結：
>
> * 當頁面載入時自動開始的檔案下載
> * 重新導向後觸發的下載
> * 按一下右鍵並選擇「將目標另存為……」
> * 使用JavaScript的連結，例如 `javascript:openLink()`
>
> 
對於這些下載類型，您可以手動呼叫函 `tl()` 數。

如果點按的連結符合退出連結和下載連結條件，則下載連結類型會優先。

## 在Adobe Experience Platform Launch中下載擴充功能

「下載擴充功能」是檔案副檔名的清單，其中包含欄位，可在設定Adobe Analytics擴充功能時，在「連結追蹤  」accordion下新增更多。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開「 [!UICONTROL 連結追蹤] 」accordion，顯示「下載 [!UICONTROL 擴充功能] 」欄位。

在欄位中輸入文字，然後按一下「新增」，將副檔名新增至 [!UICONTROL 清單]。 按一下各自的X圖示，從清單中移除副檔名。

## AppMeasurement和Launch自訂代碼編輯器中的s.linkDownloadFileTypes

變 `s.linkDownloadFileTypes` 數是逗號分隔的副檔名字串。 請勿使用空格。

如果未定義此變數，自動下載連結追蹤將無法運作(即使 `trackDownloadLinks` 是 `true`如此)。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v"
```
