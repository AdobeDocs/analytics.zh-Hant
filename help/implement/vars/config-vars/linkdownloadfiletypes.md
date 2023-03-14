---
title: linkDownloadFileTypes
description: 判斷要以下載連結形式自動追蹤的副檔名。
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 56%

---

# linkDownloadFileTypes

當 [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement)或 [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK)啟用後，當訪客點按連結時，AppMeasurement會檢查連結的URL，取得檔案類型副檔名。 如果連結URL包含相符的檔案類型，系統會自動傳送下載連結影像要求。

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
>對於這些下載類型，您可以手動傳送 [`link tracking`](../functions/tl-method.md) 呼叫。

如果點擊的連結符合退出連結和下載連結這兩個條件，則下載連結類型優先。

## 使用Web SDK擴充功能下載連結限定符

此 [!UICONTROL 下載連結限定符] 文字欄位使用regex來判斷點按的連結是否符合下載連結的資格。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往 [!UICONTROL 擴充功能] ，然後按一下 **[!UICONTROL 設定]** 按鈕 [!UICONTROL Adobe Experience Platform Web SDK].
1. 在 [!UICONTROL 資料收集]，請在 **[!UICONTROL 下載連結限定符]** 文字欄位。

## 手動實作Web SDK的下載連結限定符

[設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant) SDK使用 [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking). 欄位會對點按的URL使用規則運算式，以判斷它是否為有效的下載連結。 若 `downloadLinkQualifier` 未定義，則預設值設為 `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## 使用Adobe Analytics擴充功能下載擴充功能

「下載擴充功能」是副檔名清單，其中包含的欄位可在設定 Adobe Analytics 擴充功能時，於「[!UICONTROL 連結追蹤]」摺疊式功能表下方新增更多副檔名。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「連結追蹤」]摺疊式功能表，如此可顯示&#x200B;**[!UICONTROL 「下載擴充功能」]**&#x200B;欄位。

在欄位中輸入文字並按一下&#x200B;**[!UICONTROL 「新增」]**，將副檔名新增至清單。按一下各自的副檔名，從清單中移除副檔名 **&#39;X&#39;** 表徵圖。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.linkDownloadFileTypes

`s.linkDownloadFileTypes` 變數是以逗號分隔的副檔名字串，因此請勿使用空格。

如果此變數未定義，自動下載連結追蹤將無法發揮作用 (即便 [`trackDownloadLinks`](trackdownloadlinks.md) 是 `true`)。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
