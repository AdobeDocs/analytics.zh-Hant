---
title: linkDownloadFileTypes
description: 判斷要以下載連結形式自動追蹤的副檔名。
feature: Appmeasurement Implementation
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
role: Admin, Developer
TQID: https://experienceleague.adobe.com/xe-ClVo-348u2ash9QODi2hIdGrVv6sIeN739EfPZ7c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 419
ht-degree: 57%

---

# linkDownloadFileTypes

當[`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement)或[`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK)已啟用，且訪客點按連結時，AppMeasurement會檢查連結的URL以取得檔案型別副檔名。 如果連結URL包含相符的檔案型別，系統會自動傳送下載連結影像要求。

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
>對於這些下載型別，您可以手動傳送[`link tracking`](../functions/tl-method.md)呼叫。

如果點擊的連結符合退出連結和下載連結這兩個條件，則下載連結類型優先。

## 使用Web SDK擴充功能下載連結限定詞

[!UICONTROL 下載連結限定詞]文字欄位會使用Regex來判斷點按的連結是否符合下載連結的資格。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 移至[!UICONTROL 擴充功能]標籤，然後按一下[!UICONTROL Adobe Experience Platform Web SDK]底下的&#x200B;**[!UICONTROL 設定]**&#x200B;按鈕。
1. 在[!UICONTROL 資料彙集]下，在&#x200B;**[!UICONTROL 下載連結限定詞]**&#x200B;文字欄位中設定所要的值。

## 手動下載連結限定詞實作網頁SDK

[&#128279;](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant)使用[`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=zh-Hant#automaticLinkTracking)設定 SDK。 欄位會在點按的URL上使用Regex來判斷是否為有效的下載連結。 如果未定義`downloadLinkQualifier`，預設值會設為`\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`。

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## 使用Adobe Analytics擴充功能下載擴充功能

「下載擴充功能」是副檔名清單，其中包含的欄位可在設定 Adobe Analytics 擴充功能時，於「[!UICONTROL 連結追蹤]」摺疊式功能表下方新增更多副檔名。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往「[!UICONTROL 擴充功能]」索引標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「連結追蹤」]摺疊式功能表，如此可顯示&#x200B;**[!UICONTROL 「下載擴充功能」]**&#x200B;欄位。

在欄位中輸入文字並按一下&#x200B;**[!UICONTROL 「新增」]**，將副檔名新增至清單。 按一下各自的&#x200B;**&#39;X&#39;**&#x200B;圖示，從清單中移除副檔名。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.linkDownloadFileTypes

`s.linkDownloadFileTypes` 變數是以逗號分隔的副檔名字串， 因此請勿使用空格。

如果此變數未定義，自動下載連結追蹤將無法發揮作用 (即便 [`trackDownloadLinks`](trackdownloadlinks.md) 是 `true`)。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
