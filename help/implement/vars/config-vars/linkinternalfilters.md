---
title: linkInternalFilters
description: 使用linkInternalFilters變數可協助自動退出連結追蹤。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkInternalFilters

AppMeasurement提供自動追蹤網站外部連結的功能。 如果 [`trackExternalLinks`](trackexternallinks.md) 啟用，當訪客點按連結離開您的網站時，影像要求會直接傳送給Adobe。 與變 [`linkExternalFilters`](linkexternalfilters.md) 數會 `linkInternalFilters` 決定哪些連結被視為內部／外部連結。

如果此變數包含值，自動退出連結追蹤會以類似黑名單的方式運作。 如果連結點按不符合任何 `linkInternalFilters` 值，則會視為退出連結。 系統會針對此變數檢查整個URL。 如果 [`linkLeaveQueryString`](linkleavequerystring.md) 已啟用，則也會檢查查詢字串。

如果您同時使用 `linkInternalFilters` 和 `linkExternalFilters` 兩者，則點按的連結必須符合 `linkExternalFilters` 且不符 **，才**`linkInternalFilters` 會被視為退出連結。 如果點按的連結符合退出連結和下載連結條件，則下載連結類型會優先。

> [!NOTE] 和 `linkInternalFilters` 內 [部URL篩選器是個別功能](/help/admin/admin/internal-url-filter-admin.md) ，可用於不同用途。 此變 `linkInternalFilters` 數專用於退出連結追蹤。 內部URL篩選器是管理員設定，可協助處理流量來源維度，例如反向連結網域。

## 對外連結——在Adobe Experience Platform Launch中永不追蹤

「從不追蹤」欄位是設定Adobe Analytics擴充功能時，accordion下方以逗號分隔的篩 [!UICONTROL Link Tracking] 選器清單（通常是網域）。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Extensions] ，然後按一下「Adobe Analytics [!UICONTROL Configure] 」下的按鈕。
4. 展開accordion [!UICONTROL Link Tracking] ，以顯示欄 [!UICONTROL Outbound Links - Never Track] 位。

在此欄位中置入您不想被追蹤為退出連結的篩選器。 以逗號分隔多個網域，不含空格。

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
