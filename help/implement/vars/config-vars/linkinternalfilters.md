---
title: linkInternalFilters
description: 使用 linkInternalFilters 變數來協助自動退出連結追蹤。
feature: Variables
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 100%

---

# 連結內部篩選器

AppMeasurement 提供自動追蹤連結的功能，讓您追蹤指向網站外部的連結。如果啟用 [`trackExternalLinks`](trackexternallinks.md)，當訪客按一下連結離開您的網站時，系統會將影像要求立即傳送給 Adobe。[`linkExternalFilters`](linkexternalfilters.md) 和 `linkInternalFilters` 變數決定要將哪些連結視為內部/外部連結。

如果此變數包含值，自動退出連結追蹤將會表現出類似封鎖清單的行為。如果連結點擊與任何 `linkInternalFilters` 值不符，則會視為退出連結。系統會針對此變數檢查整個 URL。如果啟用 [`linkLeaveQueryString`](linkleavequerystring.md)，也會檢查查詢字串。

如果您同時使用 `linkInternalFilters` 和 `linkExternalFilters` 兩者，點按的連結必須符合 `linkExternalFilters` **而且**&#x200B;與 `linkInternalFilters` 不符，才會視為退出連結。如果點擊的連結符合退出連結和下載連結這兩個條件，則下載連結類型優先。

Activity Map 使用此變數來幫助確定哪些是您網站內部連結。。Adobe 建議將此變數設定為使用 Activity Map 的實施作業。

>[!NOTE]
>
>`linkInternalFilters` 和[內部 URL 篩選器](/help/admin/admin/internal-url-filter-admin.md)是不同的功能，其目的也不同。`linkInternalFilters` 變數專門用於退出連結追蹤。內部 URL 篩選器是管理員設定，能協助處理反向連結網域之類的流量來源維度。

## 對外連結 - 使用 Adobe Experience Platform 中的標記的永不追蹤

「永不追蹤」欄位是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL 連結追蹤]」摺疊式功能表下方的逗號分隔篩選清單 (通常是網域)。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「連結追蹤」]摺疊式功能表，如此可顯示[!UICONTROL 「對外連結 - 永不追蹤」]欄位。

針對您永遠不想以退出連結形式追蹤的篩選器，請將篩選器置入此欄位中請使用逗號 (不含空格) 分隔多個網域。

## AppMeasurement 和自訂程式碼編輯器中的 s.linkInternalFilters

`s.linkInternalFilters` 變數是字串，其中包含您視為網站內部的篩選器 (如網域)。請使用逗號 (不含空格) 分隔多個篩選器。

```js
s.linkInternalFilters = "example.com,example.net";
```

請將下列實施範例視為在 `adobe.com` 上實施：

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
