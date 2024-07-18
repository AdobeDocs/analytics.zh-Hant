---
title: eVar（銷售維度）
description: 繫結至產品維度的自訂變數。
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 92%

---

# eVar (銷售)

*此說明頁面說明銷售eVar作為[維度](overview.md)時的運作方式。 如需如何實作銷售eVar的相關資訊，請參閱實作使用手冊中的[eVar（銷售變數）](/help/implement/vars/page-vars/evar-merchandising.md)。*

如需銷售 eVar 如何運作的詳細討論內容，請參閱「[銷售 eVar 和產品尋找方法](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=zh-Hant)」。

測量外部促銷活動或外部搜尋詞的成功情形時，通常會想使用單一值來接收發生之任何成功事件的評分。例如，如果客戶按一下促銷活動電子郵件中的連結而前往您的網站，其隨後進行的所有購買都應評給該促銷活動。

如果是在客戶尋找多個項目時，由內部搜尋或類別瀏覽驅動的事件呢？例如，客戶在您的網站上搜尋 `"goggles"`，接著新增一組產品至購物車：

![護目鏡範例](assets/merch-example-goggles.png)

結帳前，客戶又搜尋 `"winter coat"`，然後新增了一件羽絨外套至購物車：

![外套範例](assets/merch-example-coat.png)

訪客完成此次購買後，您對 `"winter coat"` 的內部搜尋會獲得購買護目鏡的評分 (假設 eVar 使用預設的「最近」配置)。這樣對 `"winter coat"` 有利，但對行銷決策不利。

| 內部搜尋詞 | 收入 |
|---|---|
| 冬季大衣 | $157 |

## 銷售變數如何解決這個問題

銷售 eVar 可讓您在成功事件發生時，將 eVar 的目前值指派給產品。即使稍後對該特定 eVar 設定了一或多個新值，這個值仍維持繫結至該產品。

如果在上述範例中為 eVar 啟用了銷售，搜尋詞彙 `"goggles"` 就會繫結至滑雪鏡，而搜尋詞彙 `"winter coat"` 會繫結至羽絨外套。銷售 eVar 會在產品層級分配收入，每個詞彙會獲得與其相關聯之產品收入金額的評分：

| 內部搜尋詞 | 收入 |
|---|---|
| 冬季大衣 | $119 |
| 護目鏡 | $38 |

如需實作指示，請參閱[銷售 eVar](/help/implement/vars/page-vars/evar-merchandising.md)。

## 銷售變數的例項

不建議將[例項](../metrics/instances.md)量度用於銷售變數。

* 對於使用產品語法的銷售變數，例項完全不會增加。
* 對於使用轉換變數語法的銷售變數，在每次設定 eVar 時都會計算例項。不過，它會歸因於維度項目 `"None"`，除非相同的點擊上發生了以下所有情況：
   * 銷售 eVar 設定了某個值。
   * `products` 變數以某個值定義。
   * 已設定綁定事件。

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

由於轉換變數語法的使用案例大多需要 eVar 和產品變數位於不同的點擊上，因此使用「例項」量度並無實質效益。
