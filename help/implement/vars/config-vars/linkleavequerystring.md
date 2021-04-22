---
title: linkLeaveQueryString
description: 允許保留連結追蹤維度中的查詢字串。
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '289'
ht-degree: 100%

---

# linkLeaveQueryString

依預設，AppMeasurement 會將查詢字串從連結追蹤 URL 中移除。使用 `linkLeaveQueryString` 變數，可保留連結追蹤維度中的查詢字串。

對於某些退出連結和下載連結，URL 的重要部分可能會在查詢字串中。例如，下載連結 (如 `https://example.com/download.asp?filename=myfile.exe`) 的查詢字串就包含重要連結資訊。

如果連結追蹤資訊不在網站的 URL 中，就不需要使用此變數。移除連結追蹤 URL 中的查詢字串，有助於限制維度所包含的獨特值數目。

`linkLeaveQueryString` 的啟用將套用至所有連結追蹤維度 (包括自訂連結、退出連結和下載連結)。

>[!TIP]
>
> 此變數不會影響連結追蹤以外的維度。它只會影響自訂連結、退出連結和下載連結。

## Adobe Experience Platform Launch 中的保留 URL 參數

[!UICONTROL 「保留 URL 參數」]是在設定 Adobe Analytics 擴充功能時，於[!UICONTROL 「連結追蹤」]設定追蹤器下方的核取方塊。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「連結追蹤」]設定追蹤器，如此可顯示[!UICONTROL 「保留 URL 參數」]核取方塊。

如果您想在連結追蹤維度中納入查詢字串，請勾選此方塊。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.linkLeaveQueryString

`s.linkLeaveQueryString` 變數是布林值。其預設值為 `false`。

* 若將此變數設為 `true`，查詢字串會保留在連結追蹤 URL 中。
* 若將此變數設為 `false` 或未定義，連結追蹤 URL 中的查詢字串將遭到移除。

```js
s.linkLeaveQueryString = true;
```

## 範例

將此變數設為 true 時請務必小心，因為這會影響 [`linkInternalFilters`](linkinternalfilters.md)、[`linkExternalFilters`](linkexternalfilters.md) 和 [`linkDownloadFiletypes`](linkdownloadfiletypes.md) 之類的連結追蹤篩選器。

請將下列範例視為在 `adobe.com` 上實施：

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
