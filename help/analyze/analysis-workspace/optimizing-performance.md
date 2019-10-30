---
description: 'null'
seo-description: 'null'
seo-title: Analysis Workspace 效能最佳化
title: Analysis Workspace 效能最佳化
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Analysis Workspace 效能最佳化

特定因子可以影響 Analysis Workspace 中專案的效能在您開始建立專案之前，請務必先瞭解這些投稿者的身分，以便您能以最佳的方式規劃和建立專案。 以下列出影響效能的因素，以及將專案最佳化的最佳實踐。分析工作區效能是Adobe的首要工作，而且我們每天都在不斷改善。

## 區段邏輯的複雜性

複雜的區段可能對專案效能造成重大影響。增加區段複雜性的因素（影響的降序）包括：

* 運算子為"contains"、"contains any of"、"matches"、"starts with"或"ends with"
* 連續區段，特別是使用維度限制 (「之內」/「之後」) 時
* 區段使用的維度內不重複維度項目數量 (例如: 具有 10 個不重複項目的頁面 =「A」，其速度會比具有 100000 個不重複項目的頁面 =「A」更快)
* 使用的不同維度數量 (例如: 頁面 =「首頁」和頁面 =「搜尋結果」，其速度會比 eVar 1 =「紅色」和 eVar 2 =「藍色」更快)
* 多個「或」運算子 (而非「和」)
* 範圍不同的巢狀容器（例如「訪客」內「瀏覽」內的「點擊」）

**邏輯複雜性的最佳實務**

雖然有些複雜度因子無法避免，但您可以思考有哪些機會可降低您區段的複雜度。一般而言，區段條件越明確越好。例如:

* 若使用容器，在區段頂端使用單一容器，其速度會比一系列巢狀容器更快。
* 使用運算子時，"equals"會比"contains"快，而"equals any of"會比"contains any of"快。
* 若使用多個條件，「和」運算子會比一系列「或」運算子更快。此外，請尋找將許多OR陳述式簡化為單一「等於任一陳述式」的機會。

另外，[分類](/help/components/c-classifications2/c-classifications.md)可協助將許多值併入精準的群組中，讓您可從這些群組建立區段。分類群組的分段比包含許多OR陳述式或「包含」條件的區段提供效能優勢。

## 要求的資料範圍

要求的專案資料範圍將影響 Analysis Workspace 的效能。

**資料範圍的最佳實務**

盡可能，請勿拉入超出所需的資料。

記住，日期範圍 (紫色元件) 會覆蓋面板日期範圍。因此，如果您使用不同日期範圍做為欄 (例如，「上個月」、「上週」和「昨天」欄)，面板日期範圍不必跨越所有的欄日期範圍。可簡單將其設為昨天，因自由表格中使用的資料範圍會覆蓋面板。如需在 Analysis Workspace 中使用日期範圍的相關資訊，請看[這段影片](https://www.youtube.com/watch?v=ybmv6EBmhn0)。

Use [date comparison options](../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764) to pull in the specific time periods of data you want to compare. 例如，如果您需要顯示上個月的資料來與去年同用份比較，不必將面板設定為過去 13 個月的資料，只要使用比較時間範圍選項來顯示年對年的效能。

## 視覺效果的數目

一個專案中包含的圖表視覺效果數目，會影響 Analysis Workspace 的整體回應。

**視覺化數目的最佳實務**

減少專案中的視覺效果數目。Analysis Workspace 會在幕後為您新增的每個視覺效果做大量處理，因此請對報表的消費者來說最重要的視覺效果定出優先順序，並且若有需要的話，將支援的視覺效果分到其他更詳細的專案。

## 視覺效果的複雜度 (區段、量度、篩選器)

個別新增至專案的視覺化類型（例如流失與自由表格）對專案效能的影響不大。 視覺效果的複雜度會增加處理時間。增加視覺效果複雜度的因素包括:

* 要求的資料範圍，如前述
* 套用的區段數；例如，用來做為自由表格列的區段
* 使用複雜區段
* 自由表格的靜態項目列或欄
* 自由表格列所套用的篩選器
* 包含的量度數目，尤其是使用了區段的計算量度

**視覺化複雜性的最佳實務**

如果您注意到您的專案載入速度不如預期，可以的話，試著將一些區段取代為 eVar 和篩選器。

如果您發現自己時常使用公司重要資料點的區段和計算量度，請考慮改良實作，用更直接的方式擷取這些資料點。使用Adobe Experience Platform Launch和Adobe處理規則等標籤管理程式，可讓實作變更快速且易於實作。 若要深入了解如何簡化複雜區段，請見上方的「區段邏輯複雜度」。

## 面板數目

一個面板可以有許多視覺效果，因此，面板數目也會影響 Analysis Workspace 的整體回應.

**適用於面板數目的最佳實務**

不要嘗試將所有項目都加入一個專案中，而是建立可針對特定目的或利益相關者群組的不同專案。 使用標記將專案依主題組織整理，並與股東群組共用相關專案。

如果需要更多專案組織方式，記住[直接連結](https://www.youtube.com/watch?v=6IOEewflG2U)到專案也是一個做法。建立內部的專案索引，讓股東更容易找到他們要找的。

如果一個 Workspace 需要許多面板，請先摺疊面板再儲存和共用。載入專案時，Analysis Workspace 只會載入展開面板的內容。直到使用者展開，否則不會載入摺疊的面板。這種做法有兩個優點:

* 摺疊的面板可節省專案的整體載入時間
* 對報表消費者來說，摺疊的面板是以邏輯方式組織專案的好方法

## 報表套裝的大小

報表套裝的大小可能看來是個重大因素，但實際上由於 Adobe 的資料處理方式，它在專案效能上只扮演一個小角色

## 同時存取分析工作區的使用者人數

同時存取分析工作區或特定專案的使用者人數對分析工作區的效能沒有重大影響（如果使用者正在存取不同的報表套裝）。 如果同時使用者正在存取相同的報表套裝，效能將會受到影響。

## 分析工作區中的常見錯誤訊息

在與分析工作區互動時可能會遇到錯誤。 錯誤可能出於幾個原因，下面列出的是最常見的錯誤。

| 錯誤訊息 | 為什麼會發生這種情況？ |
|---|---|
| `The report suite is experiencing unusually heavy reporting. Please try again later.` | 您的組織正嘗試針對特定報表套裝執行太多的並行請求。 造成此錯誤的因素包括API請求、排程專案、排程報表、排程警報，以及提出報表請求的並行使用者。 我們建議您的報表套裝請求和排程在一天中分佈得更均勻。 |
| `A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.` | Adobe遇到需要解決的問題。 建議您透過客戶服務要求提交錯誤碼。 |
| `The request is too complex.` | 您的報表請求太大，無法執行。 此錯誤的成因是請求大小導致逾時、區段或搜尋篩選器中的相符項目太多、包含的量度太多、維度和量度組合不相容等。 我們建議您簡化您的要求。 |
| `One of the segments or the search in this visualization contains a text search that returned too many results.` | 我們建議縮小搜尋文字標準，並再次嘗試請求。 |
| `This dimension does not currently support non-default attribution models.` | 我們建議使用與 [Attribution IQ相容的維度來取代表格中的維度](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html)。 |
| `Your request failed as a result of too many columns or pre-configured rows.` | 我們建議移除某些欄或列，或考慮將它們分割為個別的視覺化。 |
