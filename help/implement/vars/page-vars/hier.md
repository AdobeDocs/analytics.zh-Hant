---
title: hier
description: 在 Adobe Analytics 中實施階層變數。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# hier

階層變數是可讓您查看網站結構的自訂變數。

>[!TIP] 此變數在舊版Adobe Analytics中較常見。 Adobe建議改 [用eVar](evar.md) 和分類。

此變數適用於網站結構中有三個以上層級的網站。 例如，媒體網站的「運動」區段可以有4個層級： `Sports`、 `Local Sports``Baseball`和 `Team name`。 如果有人瀏覽了「棒球」頁面、「運動」、「地方運動」和「棒球」，所有層級都會反映該次瀏覽。

Adobe在您的實作中支援最多5個階層變數。 在啟用階層時，請決定變數的分隔字元和階層的最大層級數。 例如，如果分隔字元是逗號，階層會如下所示：

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

請確定您的區段名稱中沒有分隔字元。 例如，如果呼叫您的其中一個區段， `Coach Griffin, Jim`請選擇逗號以外的分隔字元。 變數總限制為255位元組。 分隔字元可由多個字元組成， `||` 例如 `/|\`或，這些字元不太可能出現在變數值中。

## 範例

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
