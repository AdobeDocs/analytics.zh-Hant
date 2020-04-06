---
title: linkExternalFilters
description: 使用 linkExternalFilters 變數來協助自動退出連結追蹤。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkExternalFilters

AppMeasurement 提供自動追蹤連結的功能，讓您追蹤指向網站外部的連結。If [`trackExternalLinks`](trackexternallinks.md) is enabled, an image request is sent to Adobe right as a visitor clicks a link to leave your site. `linkExternalFilters` 和 [`linkInternalFilters`](linkinternalfilters.md) 變數決定要將哪些連結視為內部/外部連結。

如果此變數包含值，自動退出連結追蹤會表現出類似白名單的行為。如果連結點擊與任何 `linkExternalFilters` 值不符，則不視為退出連結。系統會針對此變數檢查整個 URL。If [`linkLeaveQueryString`](linkleavequerystring.md) is enabled, the query string is also examined.

>[!TIP] 只有在您明確知道要將哪些網域視為退出連結時，才使用此變數。許多組織發現，使用 `linkInternalFilters` 足以滿足其退出連結追蹤需求，因而未使用 `linkExternalFilters`。

如果您同時使用 `linkInternalFilters` 和 `linkExternalFilters` 兩者，點按的連結必須符合 `linkExternalFilters` **而且**&#x200B;與 `linkInternalFilters` 不符，才會視為退出連結。如果點按的連結符合退出連結和下載連結兩條件，下載連結類型的優先較高。

## 對外連結 - Adobe Experience Platform Launch 中的追蹤

The Track field is a comma-separated list of filters (usually domains) under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. 展開accordion [!UICONTROL Link Tracking] ，以顯示欄 [!UICONTROL Outbound Links - Track] 位。

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

<!-- The following link is an exit link because it matches the linkExternalFilters whitelist -->
<a href = "example.com">Example link 2</a>
```
