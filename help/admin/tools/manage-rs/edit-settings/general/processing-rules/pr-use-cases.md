---
description: 處理規則的常見使用案例。
subtopic: Processing rules
title: 處理規則使用案例
feature: Processing Rules
role: Admin
exl-id: 914a0d31-d256-456e-a44a-008490e86a23
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 22%

---

# 處理規則使用案例

您可在組織內使用處理規則的應用程式非常廣泛。 以下幾節將詳細說明您可能會使用它們的一些常見方式。

+++複製內容資料變數至 eVar

處理規則用於將值從[內容資料變數](/help/implement/vars/page-vars/contextdata.md)移至[Props](/help/components/dimensions/prop.md)和[eVars](/help/components/dimensions/evar.md)。 若沒有處理規則，內容資料變數就毫無意義，且不會填入 Analytics 的任何報告。

[!UICONTROL 內容變數]清單包含過去30天內傳送至報表套裝的所有變數。 如果您知道上下文資料變數的名稱但尚未將它傳送至目前的報表套裝，您可以手動新增：

![手動將內容資料變數新增至處理規則](assets/add-context-variable.png)

下列範例接受`search_term`內容資料變數並將其值放入eVar3：

| 規則集 | 值 |
| 條件 | `search_term` （內容資料）已設定 |
| 動作 | [!UICONTROL 以]覆寫`search_term` eVar3的值（內容資料） |

![顯示內容資料變數使用情況的處理規則介面熒幕擷圖](assets/set-context-data.png)

如果只有少數幾個 eVar 可填入，上述範例非常實用。如果您的組織有數百個上下文資料變數，每個變數都需要專屬 eVar，建議使用條件陳述式。符合單一處理規則的條件陳述式有數十個，方便您的組織填入報表套裝中的所有 eVar，不需受限於 150 個處理規則的上限。

下列範例會將各種上下文資料變數填入多個變數中。 一個動作也包含條件陳述式：

| 規則集 | 值 |
| 動作 | [!UICONTROL 以]覆寫`spa.billing_customer_name` eVar55的值（內容資料） |
| 動作 | 如果已設定[!UICONTROL &#x200B; （內容資料），請使用] （內容資料）覆寫`testhierarchy` Prop7的值 |
| 動作 | `testhierarchy`以[!UICONTROL 覆寫] eVar8的值（內容資料） |`spa.ims_org`

![處理規則介面的熒幕擷圖，顯示如何有條件地設定值](assets/add-conditional.png)

+++

+++使用內容資料變數設定事件

處理規則可根據[內容資料變數](/help/implement/vars/page-vars/contextdata.md)觸發事件。

[!UICONTROL 內容變數]清單包含過去30天內傳送至報表套裝的所有變數。 如果您知道上下文資料變數的名稱但尚未將它傳送至目前的報表套裝，您可以手動新增：

![手動將內容資料變數新增至處理規則](assets/add-context-variable.png)

下列規則定義會在每個包含特定內容資料變數的點選上設定事件：

| 規則集 | 值 |
| --- | --- |
| 條件 | `search_term` （內容資料）已設定 |
| 動作 | [!UICONTROL 將Event] Event1設為[!UICONTROL 自訂值] `1` |

![顯示如何設定事件的處理規則介面熒幕擷圖](assets/processing_rule_set_event.png)

+++

+++使用查詢字串引數填入變數

您可以使用查詢字串引數填入變數。 在大多數情況下，您通常會調整實施以取得所需的查詢字串值。 不過，如果您無法輕鬆調整實作以收集此資料，處理規則是個適當的替代方案。 如果發生打字錯誤或類似問題因而無法填入值，您可使用處理規則來填入值。

覆寫值之前，請務必先檢查值是否空白或包含預期值。

| 規則集 | 值 |
| --- | --- |
| 條件 | 行銷活動未設定 |
| 動作 | [!UICONTROL 以]查詢字串引數[!UICONTROL 覆寫]促銷活動的值`cpid` |

![顯示條件行銷活動邏輯的處理規則介面熒幕擷圖](assets/set-campaign-conditionally.png)

| 規則集 | 值 |
| --- | --- |
| 條件 | [!UICONTROL 查詢字串引數] `q` [!UICONTROL 已設定] |
| 動作 | [!UICONTROL 以]查詢字串引數[!UICONTROL 覆寫]個內部搜尋詞的值`q` |

![顯示內部搜尋字詞邏輯的處理規則介面熒幕擷圖](assets/populate-internal-search-terms.png)

+++

+++有條件地設定任何事件

可以根據處理規則中可用的任何條件來設定事件。 例如，您可以在頁面名稱等於「產品概述」時觸發事件。

| 規則集 | 值 |
| --- | --- |
| 條件 | 如果[!UICONTROL Page Name]等於「產品概述」 |
| 動作 | [!UICONTROL 設定事件] [!UICONTROL 產品檢視]為[!UICONTROL 自訂值] `1` |

![處理規則介面的熒幕擷圖，顯示有條件設定的事件](assets/set-product-view-event.png)

+++

+++串連類別和頁面名稱以新增子類別

您可使用串連選項結合其他值，用來填入值。

| 規則集 | 值 |
| --- | --- |
| 條件 | 無（一律執行） |
| 動作 | [!UICONTROL 以]串連值[!UICONTROL 類別+頁面名稱覆寫] eVar1的值 |

![顯示串連值的處理規則介面熒幕擷圖](assets/add-subcategory-using-concat.png)

+++

+++清除報表中的值

您可以比對值是否有拼字錯誤，並加以更新以在報表中正確顯示。

Adobe建議您儘可能使用最嚴格的比對選項，以避免不想要的覆寫。 您可以對變數執行報告，並搜尋您要使用的潛在規則條件。 字串比較不區分大小寫。

| 規則集 | 值 |
| --- | --- |
| 條件 | 如果prop1 [!UICONTROL 開頭為] &quot;[!DNL Shoping]&quot; |
| 動作 | [!UICONTROL 以]自訂值[!UICONTROL 覆寫] Prop1的值[!DNL Shopping] |

![處理規則介面的熒幕擷圖，顯示如何修正錯字](assets/clean-up-values-in-report.png)

+++

+++從點擊中移除事件

您可以使用處理規則從點選中移除或捨棄特定事件，而不變更您的實作。 如果您將事件設為自訂值`0`，則事件不會計入。

| 規則集 | 值 |
| 條件 | 無（一律執行） |
| 動作 | [!UICONTROL 將event] Event1設為[!UICONTROL 自訂值] `0` |

![處理規則介面的熒幕擷圖顯示給以移除事件](assets/remove_event.png)

+++
