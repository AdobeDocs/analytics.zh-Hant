---
title: eVar （銷售維度）
description: 繫結至產品維度的自訂變數。
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
TQID: 'https://experienceleague.adobe.com/No-Va3JzN6Qz9hBu73A5ZzKudEB1Tqa4sNPKVKAASGI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '2343'
ht-degree: 4%
---
# eVar (銷售)

>[!BEGINSHADEBOX]

*此說明頁面說明銷售eVar作為[維度](overview.md)時的運作方式。 如需如何實作銷售eVar的相關資訊，請參閱實作使用手冊中的[eVar （銷售變數）](/help/implement/vars/page-vars/evar-merchandising.md)。*

>[!ENDSHADEBOX]

銷售eVar的運作方式與標準eVar類似，只是每種產品都有專屬的副本。 持續性、配置和有效期的運作方式都相同，但每個產品各有不同。 標準eVar會針對每個訪客保留一個儲存值，而每個訪客都會收到每個成功事件的評分。 銷售eVar會針對每個產品保留一個持續值，而該值會因為該產品的成功事件而獲得評價：

* 產品A → `eVar1` = `value A`
* 產品B → `eVar1` = `value B`

每個產品的值都只能在包含該產品的點選上設定或變更。 設定後，該值會持續存在，直到它過期並僅接收該產品成功事件的評價。 變更產品A的值對產品B沒有影響。

銷售eVar只能與[`products`](/help/implement/vars/page-vars/products.md)變數搭配使用。 未與產品繫結的銷售eVar值不會獲得評分。 每個銷售eVar中，沒有產品的點選上的成功事件會歸因於`"None"`。

>[!TIP]
>
>若要將持續值繫結到產品以外的維度，請考慮在Customer Journey Analytics中使用[[!UICONTROL 繫結維度]](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/component-settings/persistence#binding-dimension)。

## 為何使用銷售eVar

當單一值不應該針對訪客購買的所有專案獲得點數時，為每個產品保留個別值很重要。 標準eVar很適合用於外部促銷活動或外部搜尋辭彙，其中一個值應該接收發生任何成功事件的評分。 例如，如果客戶按一下電子郵件行銷活動中的連結來造訪您的網站，則因此進行的所有購買都應計入該行銷活動。

內部搜尋和類別瀏覽是不同的，因為訪客經常會使用它們來尋找多個產品，每個產品的方式都不同。 例如，客戶在您的網站上搜尋 `"goggles"`，接著新增一組產品至購物車：

![護目鏡範例](assets/merch-example-goggles.png)

結帳前，客戶又搜尋`"winter coat"`，然後新增了一件羽絨外套至購物車：

![外套範例](assets/merch-example-coat.png)

當訪客完成此次購買時，內部搜尋辭彙`"winter coat"`會收到整個訂單（包括護目鏡）的評分，因為這是eVar的最新值([!UICONTROL 最近（上一個）]的預設配置)。 搜尋字詞`"goggles"`未獲得任何評價，即使它導致了部分購買：

| 內部搜尋字詞 | 收入 |
| --- | --- |
| 冬季外套 | $157 |

## 銷售eVar如何解決這個問題

如果在上述範例中為eVar啟用了銷售，搜尋字詞`"goggles"`會繫結至滑雪鏡，而搜尋字詞`"winter coat"`會繫結至羽絨外套。 銷售eVar會在產品層級分配收入，每個辭彙會收到與其繫結的產品收入金額的評分：

| 內部搜尋字詞 | 收入 |
| --- | --- |
| 冬季外套 | $119 |
| 護目鏡 | $38 |

## 繫結和配置的運作方式

銷售eVar依賴三個概念：

* **繫結**：產品與eVar值之間的關聯。 每個產品都會針對每個銷售eVar保留各自的繫結。 如同標準eVar值，繫結會在之後的點選中持續存在，直到它過期為止。 例如，若在稍後頁面上購買產品，與產品頁面上的產品繫結的值仍會獲得評分，而不會再次設定值。 值到達產品的方式取決於eVar的語法，如下所述。
* **配置**： [!UICONTROL 配置]設定決定當新值嘗試繫結到&#x200B;**已繫結**&#x200B;的產品時會發生什麼情況。 每個產品會分別評估配置，因此與不同產品繫結的銷售eVar值永遠不會互相競爭。
  * **[!UICONTROL 原始值（第一個）]**：保留現有的繫結。 在繫結過期之前，會忽略該產品的新值。
  * **[!UICONTROL 最近（上一個）]**：產品已重新繫結至新值。
* **到期**： [!UICONTROL 到期時間]設定決定繫結何時結束。 每個產品的繫結都有各自的到期日，從繫結該產品時開始計算。 例如，在[!UICONTROL 周]到期的情況下，如果產品A於星期一繫結，而產品B於星期三繫結，則產品A的繫結將於下星期一到期，而產品B的繫結將於下星期三到期。 繫結過期時，產品不再有該eVar的值，就好像標準eVar過期後沒有值一樣。 該產品的成功事件會歸因於`"None"`，直到產品再次繫結為止。

每個銷售eVar使用兩種語法之一，在[報告套裝設定](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)的[!UICONTROL 銷售]設定中設定。 語法會決定值到達產品的方式：

* **[產品語法](#product-syntax)**：值是直接在`products`變數中的每個產品上設定，並連結到該點選上的該產品。
* **[轉換變數語法](#conversion-variable-syntax)**：此值是在eVar中設定，並持續存在，就像標準eVar值。 它會繫結至相同或之後包含繫結事件的點選上的產品。

兩種語法都使用上述相同的繫結、配置和到期行為。 它們有以下不同之處：

| | 產品語法 | 轉換變數語法 |
| --- | --- | --- |
| 設定值的位置 | 在每個產品的[`products`](/help/implement/vars/page-vars/products.md)變數中 | 在[`eVar`](/help/implement/vars/page-vars/evar-merchandising.md)本身中，與標準eVar的方式相同 |
| 繫結發生時 | 在產品上設定值的任何點選上 | 在同時包含產品和已設定的繫結事件的點選上 |
| 每次點選的值 | 每個產品可以有不同的值 | 繫結點選中的每個產品都會收到相同的值 |
| 實作成果 | 較高 | Lower |

## 產品語法

使用產品語法時，會在`products`變數中的每個產品上設定eVar值。 在`products`字串中，產品的最後一個分號之後的值是其銷售eVar。 如需完整語法，請參閱[使用產品語法實作](/help/implement/vars/page-vars/evar-merchandising.md#implement-using-product-syntax)。

值會直接繫結至該點選上的產品。 未使用繫結事件。 包含產品的後續點選（例如購物車新增或購買）不需要重複值。 因為每個產品都有自己的值，所以當&#x200B;**相同點選**&#x200B;中的產品需要&#x200B;**不同**&#x200B;的值時，產品語法是唯一的選項。

+++範例：相同產品會收到兩個值

| 點擊 | `products` | `events` |
| --- | --- | --- |
| 1 | `;12345;;;;eVar1=internal keyword search` | |
| 2 | `;12345;;;;eVar1=internal campaign` | |
| 3 | `;12345;1;50` | `purchase` |

* **[!UICONTROL 原始值（第一個）]**：已忽略產品`12345`的點選2。 購買已貸記至`internal keyword search`。
* **[!UICONTROL 最近（上一個）]**：點選2重新繫結產品`12345`。 購買已貸記至`internal campaign`。

+++

+++範例：兩個產品會收到不同的值

| 點擊 | `products` | `events` |
| --- | --- | --- |
| 1 | `;productA;;;;eVar1=value A` | |
| 2 | `;productB;;;;eVar1=value B` | |
| 3 | `;productA;1;50,;productB;1;30` | `purchase` |

每個產品都會保留自己的繫結，因此配置設定在此範例中無效。 `value A`會獲得產品A收入的評分，`value B`會獲得產品B收入的評分。 這兩個值都會收到一個訂單，因為訂單包含與每個值繫結的產品。

+++

+++範例：具有相同ID和不同值的產品

訪客購買一件中號藍色T恤和一件大號紅色T恤，兩者都有父產品ID `tshirt123`，而且`eVar10`擷取子SKU：

```js
s.events = "purchase";
s.products = ";tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red";
```

每個子SKU都會收到其自己的`tshirt123`執行個體的評分。

+++

取捨是每當應發生繫結時，產品語法都需要每個產品的完整值字串。 對於通常會同時使用數個eVar的產品尋找方法，字串看起來像這樣：

```js
s.products = ";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
```

只有當訪客與產品互動後，尋找方法才會獲得評分，因此此字串通常設定在產品詳細資料頁面或購物車新增上，而不是搜尋結果頁面上。 為此，開發人員必須：

* 將尋找方法頁面中的尋找方法詳細資訊帶入產品詳細資訊頁面，或在購物車新增從結果頁面觸發時提供這些詳細資訊。
* 組合完整的`products`字串，且沒有語法錯誤。

轉換變數語法可避免兩個要求。

## 轉換變數語法

使用轉換變數語法時，此值是在eVar中設定：

```js
s.eVar1 = "internal keyword search";
```

eVar充當&#x200B;*臨時區域*。 eVar中設定的值會保留在那裡，直到捆綁事件將其與點選上的產品捆綁為止。 繫結分為兩個階段：

1. **暫存**：設定eVar時，其值會在後續點選中持續存在，直到它過期為止。 這個儲存的值是[資料摘要](/help/export/analytics-data-feed/data-feed-overview.md)中的`post_evar`資料行。 對於使用轉換變數語法的銷售eVar，階段值&#x200B;**一律會反映最近傳送的值**，不論[!UICONTROL 配置]設定為何。 每個新值都會取代先前分段值。
1. **繫結**：點選同時包含產品與設定的[!UICONTROL 銷售繫結事件]時，階段值會繫結至該點選上的每個產品。 如果產品已經繫結，[!UICONTROL 配置]會判斷新值是否取代現有的繫結。 已繫結的產品會將其值保留為[!UICONTROL 原始值（第一個）]，或重新繫結為[!UICONTROL 最近（最後一個）]。

如果eVar、`products`變數和繫結事件都設定在相同點選上，則會同時進行測試和繫結。 新值會立即繫結至該點選上的產品。

在沒有捆綁事件的產品旁邊設定eVar，不會將值與該產品繫結。 階段值在繫結至產品之前不會收到任何評分。

### 捆綁事件的功能

捆綁事件是告知Adobe將階段值捆綁至點選上產品的觸發器。

* 捆綁事件可以是標準或自訂成功事件、追蹤代碼（[!UICONTROL 促銷活動事件]）或eVar。 Prop對繫結沒有影響。
* 您可以設定多個繫結事件，例如[!UICONTROL 產品檢視事件]、[!UICONTROL 購物車新增事件]和[!UICONTROL 購買事件]。 若這些事件中有任何事件位在含有產品的點選上，則階段值會繫結至該點選上的每個產品。
* 依預設（[!UICONTROL 全部]），只要任何其他事件或eVar與產品位於相同的點選上，就會發生繫結。 如果未明確選取任何繫結事件，則會使用[!UICONTROL All]。 透過[!UICONTROL 全部]，在包含產品的點選上設定eVar一律會觸發該點選上的繫結。 先前點選上暫存的值會繫結到下一次點選，其中包含產品和任何其他事件或eVar。

+++範例：與捆綁事件繫結

考量下列點選：

```js
// Hit 1
s.eVar1 = "internal keyword search";
s.eVar2 = "sandals";

// Hit 2
s.products = ";sandal123";
s.events = "prodView";
```

如果`prodView`是兩個eVar的繫結事件，則點選2會將`internal keyword search` (`eVar1`)和`sandals` (`eVar2`)繫結至`sandal123`。 如果eVar未將`prodView`列為捆綁事件，則不會發生該eVar的捆綁。

+++

+++範例：依據產品評估配置

| 點擊 | `eVar1` | `products` | `events` |
| --- | --- | --- | --- |
| 1 | `value A` | | |
| 2 | | `;productA,;productB` | 捆綁事件 |
| 3 | `value B` | | |
| 4 | | `;productA` | 捆綁事件 |
| 5 | | `;productA;1;50,;productB;1;30` | `purchase` |

點選3之後，階段值(`post_evar1`)為具有任一配置設定的`value B`。

* **[!UICONTROL 原始值（第一個）]**：產品A已忽略點選4，因為產品A已繫結。 兩個產品都會與`value A`保持繫結，後者會收到所有購買點數。
* **[!UICONTROL 最近（上一個）]**：點選4會將產品A重新繫結至`value B`。 產品B不在點選4中，因此它保持繫結至`value A`。 產品A的購買點數歸於`value B`，產品B的購買點數歸於`value A`。

若只有一次繫結嘗試（例如僅點選1、2和5），則兩個設定會產生相同的結果。 配置只有在已繫結的產品收到另一個繫結嘗試時才重要。

+++

## 最佳實務：產品尋找方法

大多數零售網站都可從追蹤下列產品尋找方法中受益，這些方法都可作為銷售eVar：

* 內部搜尋關鍵字（例如，`eVar2`）
* 內部行銷活動追蹤代碼（例如，`eVar3`）
* 銷售或瀏覽類別（例如，`eVar4`）
* 交叉銷售連結（例如，`eVar5`）
* eVar的整體產品尋找方法，可比較所有方法，包括如產品頁面的外部連結等方法（例如，`eVar1`）

當訪客使用其中一個方法時，請將另一個尋找方法eVar設為「非」值。 否則，未使用方法的先前值可能會收到透過其他方法找到之產品的評分。 例如，在結果頁面上對「涼鞋」進行內部搜尋：

```js
s.eVar1 = "internal keyword search";
s.eVar2 = "sandals";
s.eVar3 = "non-internal campaign";
s.eVar4 = "non-browse";
s.eVar5 = "non-cross-sell";
```

使用轉換變數語法，開發人員只能設定簡單值（例如prop中的搜尋字詞），而您實作中的邏輯可填入銷售eVar。 不需要在頁面之間傳遞任何內容，也不需要內建在`products`字串中。 發生繫結的點選上仍需要`products`變數。

Adobe建議您將下列設定用於產品尋找方法eVar：

| 設定 | 值 |
| --- | --- |
| [!UICONTROL 配置] | [!UICONTROL 原始值（第一個）] |
| [!UICONTROL 有效期限] | 自動移除前（例如使用[!UICONTROL 自訂]的14或30天），產品在購物車中停留的時間。 如果購物車沒有限制，請使用[!UICONTROL 購買]。 |
| [!UICONTROL Type] | [!UICONTROL 文字字串] |
| [!UICONTROL 啟用銷售] | [!UICONTROL 已啟用] |
| [!UICONTROL 銷售] | [!UICONTROL 轉換變數語法] |
| [!UICONTROL 銷售繫結事件] | [!UICONTROL 產品檢視事件]、[!UICONTROL 購物車新增事件]和[!UICONTROL 購買事件] |

如需各個設定的說明，請參閱「管理員指南」中的[轉換變數](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)。

+++為什麼原始值（第一個）而不是最近（最後一個）

訪客經常會重新找到他們已檢視或加入購物車的產品。 例如：

1. 訪客搜尋「涼鞋」，並從結果頁面新增`sandal123`至購物車。 產品繫結至`internal keyword search`。
1. 三天後，訪客瀏覽至&#x200B;**女性>鞋子>涼鞋** (`eVar1` = `browse`)，再次檢視`sandal123`，然後購買。

透過[!UICONTROL 最近（上一個）]，步驟2中的產品檢視會將`sandal123`重新繫結至`browse`，然後再接收購買點數。 原本找到產品的方法不會收到任何專案。

透過[!UICONTROL 原始值（第一個）]，步驟2中的繫結嘗試會被忽略，且`internal keyword search`會保留評分。

如果訪客從未購買過產品，則過期時間會移除繫結，因此訪客使用的下一個尋找方法可能會繫結到產品。 這就是為什麼[!UICONTROL 有效期限]應該與產品在購物車中的保留時間相符。

+++

## 銷售eVar上的例項

不建議將預設[執行個體](../metrics/instances.md)量度用於銷售變數。

* 對於使用產品語法的銷售變數，例項完全不會增加。
* 對於使用轉換變數語法的銷售變數，在每次設定 eVar 時都會計算例項。 不過，除非相同的點選上發生下列所有情況，否則執行個體會歸因於維度專案`"None"`：
  * 銷售 eVar 設定了某個值。
  * `products` 變數以某個值定義。
  * 已設定繫結事件。

由於轉換變數語法的使用案例大多需要eVar和產品變數位於不同的點選上，因此預設的例項量度使用起來並不實際。

若要計算使用轉換變數語法傳送之每個值的執行個體，請將&#x200B;**上次接觸** [歸因模型](/help/analyze/analysis-workspace/attribution/overview.md)套用至執行個體量度。 歸因模型使用每次點選時傳送的值，而非階段值或產品繫結。 回顧期間並不重要，因為無論eVar的配置設定為何，「上次接觸」都會將每個值計入傳送所在的點選上。

![歸因選取](assets/attribution-select.png)
