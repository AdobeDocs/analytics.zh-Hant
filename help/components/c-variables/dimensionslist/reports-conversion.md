---
title: eVar
description: 可用於報告的自訂維度。
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# eVar

*此說明頁面說明eVar如何以維度運作。 如需如何實作eVar的詳細資訊，請參[閱實作使用指南](/help/implement/vars/page-vars/evar.md)中的eVar。*

eVar 是自訂變數，您可以視需要使用。如果您有解決 [方案設計檔案](/help/implement/prepare/solution-design.md)，則組織的大部分特定維度都會變成eVar。 依預設，eVar會持續存在超過其設定的點擊。 您可以在報表套裝設定的「轉換變數」 [下自訂其到期](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) 和配置。

## eVar的運作方式

當您傳送資料至Adobe Analytics時，資料收集伺服器會將點擊轉譯為具有數百欄的單一資料列。 每個eVar專有兩欄；一個用於直接資料收集，另一個用於持續值。

* 標準欄包含從影像要求傳送至Adobe的資料。
* 「post」欄包含永久性資料，這取決於eVar的過期和配置。

在幾乎所有情況下，報 `post_evar` 表都會使用欄。

### eVar如何與量度關聯

成功事件和eVar通常會在不同的影像要求中定義。 此欄 `post_evar` 可讓eVar值與事件建立關聯，以顯示報告中的資料。 以下列瀏覽為例：

1. 訪客在您的首頁進入您的網站。
2. 他們使用您網站的內部搜尋來搜尋「貓」。 您的實作會將eVar1設為內部搜尋。
3. 他們檢視產品，並完成結帳程式。

原始資料的簡化版本看起來類似下列：

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* 欄會 `visitor_id` 將點擊連結至相同的訪客。 在實際原始資料中，串連的訪客ID `visid_high` 值 `visid_low` 並決定其值。
* 欄會 `pagename` 填入「頁面」維度。
* 欄會 `evar` 決定eVar1明確設定時的點擊。
* 此 `post_evar1` 值會包含上一個值，視報表套裝設定下變數的配置和有效期設定而定。
* 欄包 `event_list` 含所有量度資料。 在此範例中， `event1` 是「搜尋」，而其他事件則是標準購物車量度。 在實際原始資料中， `event_list` 包含一組逗號分隔的數字，其中查閱表格會將這些數字與量度系結。

### 將資料收集轉換為報告

Adobe Analytics中的工具（例如分析工作區）可處理此收集的資料。 例如，如果您使用eVar1作為維度，而「訂購」作為度量提取報表，您會看到類似下列的報表：

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

分析工作區使用下列邏輯提取此報表：

* 檢視所有 `event_list` 值，並挑選所有點擊的 `purchase` 項目。
* 在這些點擊中，顯示 `post_evar1` 值。

### 分配和過期的重要性

由於分配和到期會決定哪些值會持續存在，因此對於從分析實作中獲取最大價值至關重要。 Adobe強烈建議您在組織內討論如何處理（配置）每個eVar的多個值，以及eVar停止持續資料（過期）的時間。

* 依預設，eVar會使用上一個配置。 新值會覆寫持續值。
* 依預設，eVar會使用瀏覽的過期時間。 瀏覽結束後，值即停止在欄中逐行復 `post_evar` 制。

您可以在報表套裝設定的「轉換變數」下 [變更eVar配置](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) 和有效期。
