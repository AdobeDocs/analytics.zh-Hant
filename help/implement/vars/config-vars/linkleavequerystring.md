---
title: linkLeaveQueryString
description: 允許在連結追蹤維度中保留查詢字串。
translation-type: tm+mt
source-git-commit: e500332fe16887fa004858b07b59644837e183aa

---


# linkLeaveQueryString

依預設，AppMeasurement會從連結追蹤URL移除查詢字串。 使用linkLeaveQueryString變數，在連結追蹤維度中保留查詢字串。

對於某些退出連結和下載連結，URL的重要部分可以位於查詢字串中。 例如，下載連結（例如）在查 `https://example.com/download.asp?filename=myfile.exe` 詢字串中包含重要連結資訊。

如果連結追蹤資訊不在您網站的URL中，則不需要使用此變數。 從連結追蹤URL移除查詢字串有助於限制維度所包含的唯一值數目。

啟用 `linkLeaveQueryString` 功能會套用至所有連結追蹤維度（包括自訂連結、退出連結和下載連結）。

> [!TIP] 此變數不會影響連結追蹤以外的維度。 它只會影響自訂連結、退出連結和下載連結。

## 在Adobe Experience Platform Launch中保留URL參數

[!UICONTROL 設定Adobe Analytics擴充功能時] ,「保留URL參數」是「連 [!UICONTROL 結追蹤] 」accordion下方的核取方塊。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開「連 [!UICONTROL 結追蹤] 」accordion，此會顯示「保留URL [!UICONTROL 參數」核取方塊] 。

如果您想在連結追蹤維度中包含查詢字串，請勾選此方塊。

## AppMeasurement和Launch自訂代碼編輯器中的s.linkLeaveQueryString

變 `s.linkLeaveQueryString` 數是布林值。 Its default value is `false`.

* 若此變數設為，則查詢 `true`字串會保留在連結追蹤URL中。
* 如果此變數設為或未 `false` 定義，則會從連結追蹤URL移除查詢字串。

```js
s.linkLeaveQueryString = true;
```

## 範例

將此變數設為true時請務必小心，因為這會影響連結追蹤篩選 `linkInternalFilters`器， `linkExternalFilters`例如 `linkDownloadFiletypes`、。

請將下列範例視為已開啟 `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
