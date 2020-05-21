---
title: eVar
description: 可用於報表的自訂維度。
translation-type: ht
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# eVar

*此說明頁面將說明 eVar 做為維度的運作方式。如需實作 eVar 的相關資訊，請參閱實作使用手冊中的[eVar](/help/implement/vars/page-vars/evar.md)。*

eVar 是自訂變數，您可以視需要使用。如果您有[解決方案設計文件](/help/implement/prepare/solution-design.md)，則貴組織的大部分特定維度最終都會變成 eVar。依預設，eVar 可存留於其設定的點擊之外。您可以在報表套裝設定中的[「轉換變數」](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)下自訂其到期日和配置。

## eVar 的運作方式

當您傳送資料至 Adobe Analytics 時，資料收集伺服器會將點擊轉換為有數百欄的單一資料列。每個 eVar 有兩個專用欄位；一個供直接資料收集用，另一個則供持續值用。

* 標準欄包含影像要求傳送至 Adobe 的資料。
* 「Post」欄包含持續資料，這取決於 eVar 的到期日和配置。

在大部分情況下，報表都會使用 `post_evar` 欄。

### eVar 連結至量度的方式

成功事件和 eVar 通常定義在不同的影像要求中。`post_evar` 欄可讓 eVar 值連結至事件，並顯示報表中的資料。以下列造訪為例：

1. 訪客造訪您的網站，首先停留在首頁上。
2. 他們使用您網站的內部搜尋功能來搜尋「貓」。您的實作會為內部搜尋設定 eVar1。
3. 他們檢視產品，並完成結帳程序。

原始資料的簡化版本看起來類似下列結果：

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* `visitor_id` 欄會將點擊連結至相同的訪客。在實際原始資料中，`visid_high` 和 `visid_low` 的串連值將決定訪客 ID。
* `pagename` 欄中會填入「頁面」維度。
* `evar` 欄會決定 eVar1 明確設定時的點擊。
* `post_evar1` 包含先前值 (取決於報表套裝設定下的變數配置和到期日設定)。
* `event_list` 欄包含所有量度資料。在此範例中，`event1` 是「搜尋」，其他事件則是標準購物車量度。在實際原始資料中，`event_list` 包含一組以逗號分隔的數字，而查找表格會將這些數字連結至量度。

### 將資料收集轉換為報表

Adobe Analytics 中的工具 (例如 Analysis Workspace) 運作時，會使用這份收集來的資料。例如，如果您用 eVar1 作為維度，並用「訂單」作為量度來提取報表，就會看到類似下列的報表：

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace 使用下列邏輯提取此報表：

* 檢視所有 `event_list` 值，並挑選出所有包含 `purchase` 的點擊。
* 顯示這些點擊中的 `post_evar1` 值。

### 配置和到期日的重要性

由於配置和到期日會決定哪些值會能持續存在，因此在從 Analytics 實施中取得最多值時十分重要。Adobe 強烈建議您與貴組織討論要如何處理 (配置) 每個 eVar 的多個值，以及讓 eVar 停止保存資料的時間 (到期日)。

* 依預設，eVar 會使用最後一個配置。新值會覆寫持續值。
* 依預設，eVar 會使用造訪的到期日。造訪結束後，值即停止在 `post_evar` 欄中逐列複製。

您可以在報表套裝設定中的[「轉換變數」](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)下變更 eVar 配置和到期日。
