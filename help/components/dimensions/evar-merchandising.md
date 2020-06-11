---
title: eVar（銷售）
description: 與產品維度關聯的自訂變數。
translation-type: tm+mt
source-git-commit: 1968162d856b6a74bc61f22f2e5a6b1599d04c79
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 25%

---


# eVar（銷售）

*此說明頁面說明銷售eVar如何以維度運作。 For information on how to implement merchandising eVars, see[eVars](/help/implement/vars/page-vars/evar.md)in the Implement user guide.*

測量外部促銷活動或外部搜尋詞的成功情形時，通常會想使用單一值來接收發生之任何成功事件的評分。例如，如果客戶按一下促銷活動電子郵件中的連結而前往您的網站，其隨後進行的所有購買都應評給該促銷活動。

當客戶尋找多個項目時，由內部搜尋或類別瀏覽驅動的事件會如何？ For example, a customer searches your site for `"goggles"`, then adds a pair to their cart:

![護目鏡範例](assets/merch-example-goggles.png)

Before checkout, the customer searches for `"winter coat"`, then adds a down jacket to the to their cart:

![外套範例](assets/merch-example-coat.png)

當訪客完成此次購買時，您會有購買護目鏡的內部搜尋 `"winter coat"` （假設eVar使用預設的「最近」配置）。 Good for `"winter coat"`, but bad for marketing decisions:

| 內部搜尋詞 | 收入 |
|---|---|
| 冬季大衣 | $157 |

## 銷售變數如何解決這個問題

銷售eVar可讓您在發生成功事件時，將eVar的目前值指派給產品。 即使稍後對該特定 eVar 設定了一或多個新值，這個值仍維持繫結至該產品。

If merchandising is enabled for the eVar in the previous example, the search term `"goggles"` is tied to the snow goggles, and the search term `"winter coat"` is tied to the down jacket. 銷售eVar會在產品層級分配收入，因此每個期限都會收到與期限相關之產品收入金額的評分：

| 內部搜尋詞 | 收入 |
|---|---|
| 冬季大衣 | $119 |
| 護目鏡 | $38 |

如需實 [施指示](/help/implement/vars/page-vars/evar-merchandising.md) ，請參閱銷售eVar。

## 銷售變數的例項

不建 [議在銷售變數上使用「例項](../metrics/instances.md) 」量度。

* 對於使用產品語法的銷售變數，例項根本不會增加。
* 對於使用轉換變數語法的銷售變數，每次設定eVar時都會計算例項。 不過，它會歸因於維度值，除 `"None"` 非下列所有項目都發生在相同的點擊上：
   * 銷售eVar會以值設定。
   * 變 `products` 數以值定義。
   * 已設定綁定事件。

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

由於轉換變數語法的大部分使用案例都需要eVar和產品變數在不同點擊上，因此使用「例項」量度並不現實。
