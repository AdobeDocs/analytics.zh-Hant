---
title: linkDownloadFileTypes
description: 判斷要以下載連結形式自動追蹤的副檔名。
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 49%

---

# linkDownloadFileTypes

當 [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement)或 [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK)已啟用，訪問者按一下連結時，AppMeasurement會檢查連結的URL以查找檔案類型擴展。 如果連結URL包含匹配的檔案類型，則自動發送下載連結影像請求。

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
>對於這些下載類型，您可以手動發送 [`link tracking`](../functions/tl-method.md) 呼叫。

如果點擊的連結符合退出連結和下載連結這兩個條件，則下載連結類型優先。

## 使用Web SDK擴展下載連結限定符

的 [!UICONTROL 下載連結限定符] 文本欄位使用regex來確定按一下的連結是否屬於下載連結。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的標記屬性。
1. 轉到 [!UICONTROL 擴展] ，然後按一下 **[!UICONTROL 配置]** 按鈕 [!UICONTROL Adobe Experience PlatformWeb SDK]。
1. 下 [!UICONTROL 資料收集]，在 **[!UICONTROL 下載連結限定符]** 的子菜單。

## 手動實現Web SDK的下載連結限定符

[配置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant) SDK使用 [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking)。 該欄位使用按一下的URL上的regex來確定它是否是有效的下載連結。 如果 `downloadLinkQualifier` 未定義，預設值設定為 `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`。

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## 使用Adobe Analytics擴展下載擴展

「下載擴充功能」是副檔名清單，其中包含的欄位可在設定 Adobe Analytics 擴充功能時，於「[!UICONTROL 連結追蹤]」摺疊式功能表下方新增更多副檔名。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
2. 按一下所需的標記屬性。
3. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「連結追蹤」]摺疊式功能表，如此可顯示&#x200B;**[!UICONTROL 「下載擴充功能」]**&#x200B;欄位。

在欄位中輸入文字並按一下&#x200B;**[!UICONTROL 「新增」]**，將副檔名新增至清單。通過按一下其各自的檔案副檔名，從清單中刪除檔案副檔名 **「X」** 表徵圖

## AppMeasurement中的s.linkDownloadFileTypes和Analytics擴展自定義代碼編輯器

`s.linkDownloadFileTypes` 變數是以逗號分隔的副檔名字串，因此請勿使用空格。

如果此變數未定義，自動下載連結追蹤將無法發揮作用 (即便 [`trackDownloadLinks`](trackdownloadlinks.md) 是 `true`)。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
