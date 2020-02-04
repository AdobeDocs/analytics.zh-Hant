---
title: linkInternalFilters
description: 使用linkInternalFilters變數可協助自動退出連結追蹤。
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkInternalFilters

AppMeasurement提供自動追蹤網站外部連結的功能。 如果 `trackExternalLinks` 是 `true`這樣，當訪客點按連結離開您的網站時，影像要求會直接傳送給Adobe。 與變 `linkTrackExternalFilters` 數會 `linkTrackInternalFilters` 決定哪些連結被視為內部／外部連結。

如果此變數包含值，自動退出連結追蹤會以類似黑名單的方式運作。 如果連結點按不符合任何 `linkInternalFilters` 值，則會視為退出連結。 系統會針對此變數檢查整個URL。 如果 `linkLeaveQueryString` 是 `true`，則也會檢查查詢字串。

如果您同時使用 `linkInternalFilters` 和 `linkExternalFilters` 兩者，則點按的連結必須符合 `linkExternalFilters` 且不符 **，才**`linkInternalFilters` 會被視為退出連結。 如果點按的連結符合退出連結和下載連結條件，則下載連結類型會優先。

> [!NOTE] 內 `linkInternalFilters` 部URL篩選器是個別功能，可用於個別用途。 此變 `linkInternalFilters` 數專用於退出連結追蹤。 內部URL篩選器是管理員設定，可協助處理流量來源維度，例如反向連結網域。 See [Internal URL filters](/help/admin/admin/internal-url-filter-admin.md) in the Admin user guide.

## 對外連結——在Adobe Experience Platform Launch中永不追蹤

「從不追蹤」欄位是設定Adobe Analytics擴充功能時，「連結追蹤」accordion下方以逗號分隔的篩選器清單（通常是網域）。 

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開「 [!UICONTROL 連結追蹤] 」accordion，其中顯示「 [!UICONTROL 出站連結——永不追蹤」欄位] 。

在此欄位中置入您不想被追蹤為退出連結的篩選器。 以逗號分隔多個網域，毋需空格。

## AppMeasurement和Launch自訂代碼編輯器中的s.linkInternalFilters

變 `s.linkInternalFilters` 數是包含您認為是網站內部的篩選器（例如網域）的字串。 使用逗號（不含空格）分隔多個篩選器。

```js
s.linkInternalFilters = "example.com,example.net,example.org";
```

請將下列實作範例視為已開啟 `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.com">Example link 2</a>
```
