---
title: hier
description: 在 Adobe Analytics 中實施階層變數。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '185'
ht-degree: 100%

---


# hier

階層變數是可讓您查看網站結構的自訂變數。

>[!TIP]
>
>此變數在舊版 Adobe Analytics 中較常見。Adobe 建議改用 [eVar](evar.md) 和分類。

此變數對於擁有超過三層結構的網站很實用。例如，媒體網站的「運動」區段可以有 4 個層級：`Sports`、`Local Sports`、`Baseball` 和 `Team name`。若有人瀏覽了「棒球」頁面，則「運動」、「地方運動」和「棒球」等層級全都會反映該次瀏覽。

Adobe 在實施中支援最多 5 個階層變數。在啟用階層時，請決定要用於變數的分隔字元，以及該階層的最大層級數。舉例來說，如果分隔字元是逗號，階層會如下所示：

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

請確定您的區段名稱皆未包含分隔字元。舉例來說，如果您其中一個區段名為 `Coach Griffin, Jim`，請選擇逗號以外的分隔字元。變數總上限為 255 個位元組。分隔字元可由多個字元組成，如 `||` 或 `/|\`，這些字元不太可能出現在變數值中。

## 範例

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
