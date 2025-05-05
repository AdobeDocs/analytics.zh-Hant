---
title: linkExternalFilters
description: 使用 linkExternalFilters 變數來協助自動退出連結追蹤。
feature: Variables
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 91%

---

# linkExternalFilters

AppMeasurement 提供自動追蹤連結的功能，讓您追蹤指向網站外部的連結。如果啟用 [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) 或 [`clickCollectionEnabled`](trackexternallinks.md) (Web SDK)，當訪客按一下連結離開您的網站時，系統會將影像要求立即傳送給 Adobe。 `linkExternalFilters` 和 [`linkInternalFilters`](linkinternalfilters.md) 變數決定要將哪些連結視為內部/外部連結。

如果此變數包含值，自動退出連結追蹤將會表現出類似允許清單的行為。 如果連結點擊與任何 `linkExternalFilters` 值不符，則不視為退出連結。系統會針對此變數檢查整個 URL。如果啟用 [`linkLeaveQueryString`](linkleavequerystring.md)，也會檢查查詢字串。

>[!TIP]
>
> 只有在您明確知道要將哪些網域視為退出連結時，才使用此變數。許多組織發現，使用 `linkInternalFilters` 足以滿足其退出連結追蹤需求，因而未使用 `linkExternalFilters`。

如果您同時使用 `linkInternalFilters` 和 `linkExternalFilters` 兩者，點按的連結必須符合 `linkExternalFilters` **而且**&#x200B;與 `linkInternalFilters` 不符，才會視為退出連結。如果點擊的連結符合退出連結和下載連結這兩個條件，則下載連結類型優先。

## Web SDK 中的退出連結

如果退出連結目標網域與目前的 `window.location.hostname` 不同，則連結會以退出連結自動符合條件。 Web SDK 不提供任何設定變數來修改自動退出連結檢測。 如果您需要自訂以退出連結自動符合條件的網域，您可以在 `onBeforeEventSend` 回呼中使用自訂邏輯。

有關詳細資訊，請參閱 Web SDK 文件中的[自動連結追蹤](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=zh-Hant#automaticLinkTracking)。

## 使用Adobe Analytics擴充功能追蹤對外連結

「追蹤」欄位是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL 連結追蹤]」摺疊式功能表下方的逗號分隔篩選清單 (通常是網域)。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「連結追蹤」]摺疊式功能表，如此可顯示[!UICONTROL 「對外連結 - 追蹤」]欄位。

在此欄位中置入要一律視為外部的篩選器。請使用逗號 (不含空格) 分隔多個網域。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.linkExternalFilters

`s.linkExternalFilters` 變數是字串，其中包含您要視為退出連結的篩選器 (如網域)。請使用逗號 (不含空格) 分隔多個網域。

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

請將下列實施範例視為在 `adobe.com` 上實施：

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is NOT considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters allowlist -->
<a href = "example.com">Example link 2</a>
```
