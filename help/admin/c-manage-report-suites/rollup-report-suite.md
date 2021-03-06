---
description: 報表套裝類型的說明，以及全域報表套裝和統計報表套裝的比較。
title: 報表套裝做法
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: ht
source-wordcount: '973'
ht-degree: 100%

---

# 報表套裝做法

<!-- change filename since page name changed? -->

您可以將報表套裝設定為&#x200B;*全域報表套裝*&#x200B;或&#x200B;*統計報表套裝*。

## 全域報表套裝

全域報表套裝可從您的組織擁有的所有網域和應用程式中收集資料。 它需要實作，才能傳送所有影像要求給單一報表套裝。

Adobe 建議您在大多數情況下都實作全域報表套裝。 請參閱「[全域報表套裝考量事項](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html)」，以了解實作全域報表套裝的優點。

您可以使用&#x200B;*多套裝標記*&#x200B;和&#x200B;*虛擬報表套裝*&#x200B;做法，將貴公司的部分全域報表套裝資料提供給不同的一般用戶：

* **多套裝標記**：多套裝標記不僅可讓您向全域報表套裝傳送影像要求，也可傳送給個別子報表套裝。 所有報表套裝中都會針對全域報表資料進行重複資料刪除。

   例如，您可以收集一個全域報表套裝中的所有資料，也可根據品牌、地區或其他區別條件來設定次要報表套裝。 貴公司的不同團隊可能會聚焦於報表套裝中與其相關的資料。

   若要使用多套裝標記，請實作子報表套裝以及包含子報表套裝中的所有資料的全域報表套裝。 您網頁和應用程式的追蹤代碼將包含全域報表套裝的報表套裝 ID (RSID) 以及適用的子報表套裝的 RSID。<!-- Wording/be more specific? And include any links? -->

   影像要求中會針對每個報表套裝發出個別伺服器呼叫。 對子報表套裝的呼叫為次要呼叫。

* **虛擬報表套裝**：[虛擬報表套裝](/help/components/vrs/vrs-about.md)是對全域報表套裝中所收集的指定區段的查詢，可提供給指定的使用者群組使用。 虛擬報表套裝可讓您為不同的一般用戶組織報表元素，而不需要使用多套裝標記，所以可避免次要伺服器呼叫。

   若要使用虛擬報表套裝，請實作全域報表套裝，然後剖析資料來建立已套用特定區段並包含特定群組權限的虛擬報表套裝。 您可以在虛擬報表套裝管理員 ([!UICONTROL 元件] > [!UICONTROL 虛擬報表套裝]) 中建立虛擬報表套裝。 如需詳細資訊，請參閱「[虛擬報表套裝工作流程](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)」。

使用虛擬報表套裝來取代多套裝標記通常是最佳做法，但虛擬報表套裝有一些限制。 請參閱「[虛擬報表套裝和多套裝標記考量事項](/help/components/vrs/vrs-considerations.md)」，以判斷哪一種報表套裝做法是符合貴公司需求的最佳選擇。 若要了解虛擬報表套裝與多套裝標記功能的深入比較，請參閱「[虛擬報表套裝和多套裝標記的比較](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)」。

## 統計報表

>[!NOTE]
>
>[!DNL Reports & Analytics] 是唯一支援統計報表的工具，Adobe 不再建議使用統計。 請考慮改為搭配多套裝標記或虛擬報表套裝使用全域報表套裝。

統計報表是多個報表套裝中資料的簡單彙總，不會刪除重複資料，也沒有任何區段或資料劃分。 統計不需要實作程式碼。 若要使用統計報表，請[實作子報表套裝](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)然後[將其合併到統計報表中](/help/admin/c-manage-report-suites/t-rollups.md) (使用[!UICONTROL 管理員工具])。

統計報表是免費的：子報表套裝會產生自己的伺服器呼叫，但統計報表不會產生額外的呼叫。 統計報表是舊的功能，有許多限制。

### 統計報表的限制 {#limitations-rollups}

* 統計報表會提供總計資料，但不會報告報表中的個別值。 例如，eVar1 值不會納入其中，但其彙總值則可納入。
* 當統計報表結合各報表套裝中的資料時，不會進行重複資料刪除。
* 統計會在半夜執行。
* 當您新增報表套裝至現有的統計時，歷史資料不包含在統計中。
* 若要讓統計有效運作，所有子報表套裝都必須含有資料。 如果新的報表套裝被納入統計中，請務必至少傳送一個頁面檢視給各個報表套裝。
* 統計報表套裝最多可包含 40 個子報表套裝。
* 統計報表套裝最多可包含 100 個事件。
* 統計報表套裝中包含的資料不支援劃分或區段功能。
* 頁面報表已替換為最受歡迎的網站報表，後者會報告子套裝層級的量度。

## 全域報表套裝和統計報表功能的比較

**次要伺服器呼叫**：統計不會產生任何超出單一報表套裝收集範圍的額外伺服器呼叫。如果您的組織使用多套裝標記，系統會針對影像請求中所包含的每個額外報表套裝進行次要伺服器呼叫。

>[!TIP]
>
>如果您只搭配[虛擬報表套裝](/help/components/vrs/vrs-considerations.md)使用全域報表套裝，就不需要進行次要伺服器呼叫。

**實作變更**：統計不需要變更任何實作，而全域報表套裝則需要您在實作中加入全域報表套裝 ID。

**複製**：全域報表套裝會複製獨特訪客，但是統計不會。例如，使用者若在同一天內瀏覽您的三個網域，統計會計算三個每日獨特訪客。全域報表套裝會記錄一個獨特訪客。

**時段**：統計只會在每晚的午夜處理，而全域報表套裝會以標準延遲報告資料。

**幅度**：統計無法在報表套裝之間通訊。全域報表套裝可歸因於報表套裝之間的轉換變數，也能提供所有報表套裝的路徑分析。

**歷史資料**：統計可以彙總歷史資料，而全域報表套裝只會報告從其實作的點開始的資料。

**報表**：全域報表套裝會針對所有維度提供資訊；統計只提供高階報表的彙整資料。

**支援的產品**：統計只能用於 Reports &amp; Analytics，在 Analysis Workspace 或 Data Warehouse 中都不支援。 全域報表套裝可用於所有產品。

**彙總報表套裝數量**：統計最多只支援 40 個子報表套裝。無論您擁有多少網域或應用程式，皆可實作全域報表套裝。
