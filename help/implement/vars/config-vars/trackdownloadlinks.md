---
title: trackDownloadLinks
description: 啟用或停用下載連結的自動連結追蹤。
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 51%

---

# trackDownLoadLinks

Adobe 提供追蹤下載連結功能，使用者不需要手動設定每個下載連結的 [`tl()`](../functions/tl-method.md) 方法。如果您想要使用下載連結的自動連結追蹤功能，請啟用此變數。

啟用後，AppMeasurement 會將任何點按的連結 URL 與 [`linkDownloadFileTypes`](linkdownloadfiletypes.md) 中的值比較。如果有相符項目，下載連結追蹤呼叫就會自動引發。

## 使用Web SDK擴展啟用或禁用按一下集合

使用 [!UICONTROL 啟用按一下資料收集] 複選框。 此複選框處理退出和下載連結。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的標記屬性。
1. 轉到 [!UICONTROL 擴展] ，然後按一下 **[!UICONTROL 配置]** 按鈕 [!UICONTROL Adobe Experience PlatformWeb SDK]。
1. 下 [!UICONTROL 資料收集]，按一下 **[!UICONTROL 啟用按一下資料收集]** 複選框。

## 啟用或禁用手動實現Web SDK的按一下集合

使用 [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled)。 該欄位是一個布爾值，它確定是否自動收集與連結按一下相關聯的資料。 其預設值為 `true`。將此值設定為 `false` 的子菜單。 此設定處理下載連結和退出連結的自動連結跟蹤。

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## 使用Adobe Analytics擴展跟蹤下載連結

「追蹤下載連結」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL 連結追蹤]」摺疊式功能表下方的勾選方塊。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
2. 按一下所需的標記屬性。
3. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「連結追蹤」]摺疊式功能表，如此可顯示[!UICONTROL 「追蹤下載連結」]勾選方塊。

按一下勾選方塊以啟用自動下載連結追蹤。

## AppMeasurement中的s.trackDownloadLinks和Analytics擴展自定義代碼編輯器

`s.trackDownloadLinks` 是指示啟用或停用自動下載連結追蹤的布林值。 如果您不想追蹤下載連結，或想要手動呼叫 `tl()` 方法來追蹤下載內容，請將此變數設為 `false`。

```js
s.trackDownloadLinks = true;
```
