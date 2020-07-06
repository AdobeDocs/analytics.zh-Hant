---
title: linkExternalFilters
description: 使用 linkExternalFilters 變數來協助自動退出連結追蹤。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 95%

---


# linkExternalFilters

AppMeasurement 提供自動追蹤連結的功能，讓您追蹤指向網站外部的連結。如果啟用 [`trackExternalLinks`](trackexternallinks.md)，當訪客按一下連結離開您的網站時，系統會將影像要求立即傳送給 Adobe。`linkExternalFilters` 和 [`linkInternalFilters`](linkinternalfilters.md) 變數決定要將哪些連結視為內部/外部連結。

如果此變數包含值，自動退出連結追蹤的運作方式就像允許清單。 如果連結點擊與任何 `linkExternalFilters` 值不符，則不視為退出連結。系統會針對此變數檢查整個 URL。如果啟用 [`linkLeaveQueryString`](linkleavequerystring.md)，也會檢查查詢字串。

>[!TIP]
>
> 只有在您明確知道要將哪些網域視為退出連結時，才使用此變數。許多組織發現，使用 `linkInternalFilters` 足以滿足其退出連結追蹤需求，因而未使用 `linkExternalFilters`。

如果您同時使用 `linkInternalFilters` 和 `linkExternalFilters` 兩者，點按的連結必須符合 `linkExternalFilters` **而且**&#x200B;與 `linkInternalFilters` 不符，才會視為退出連結。如果點按的連結符合退出連結和下載連結兩條件，下載連結類型的優先較高。

## 對外連結 - Adobe Experience Platform Launch 中的追蹤

「追蹤」欄位是在設定 Adobe Analytics 擴充功能時，於[!UICONTROL 「連結追蹤」]設定追蹤器下方的逗號分隔篩選器清單 (通常是網域)。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「連結追蹤」]設定追蹤器，如此可顯示[!UICONTROL 「對外連結 - 追蹤」]欄位。

在此欄位中置入要一律視為外部的篩選器。請使用逗號 (不含空格) 分隔多個網域。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.linkExternalFilters

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
