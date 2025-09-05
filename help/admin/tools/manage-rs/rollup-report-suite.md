---
description: 全域報表套裝說明
title: 全域報表套裝
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 95%

---

# 全域報表套裝

全域報表套裝可從您的組織擁有的所有網域和應用程式中收集資料。 它需要實作，才能傳送所有影像要求給單一報表套裝。

Adobe 建議您在大多數情況下都實作全域報表套裝。 請參閱「[全域報表套裝考量事項](/help/implement/prepare/global-rs.md)」，以了解實作全域報表套裝的優點。

您可以使用&#x200B;*多套裝標記*&#x200B;和&#x200B;*虛擬報表套裝*&#x200B;做法，將貴公司的部分全域報表套裝資料提供給不同的一般用戶：

* **多套裝標記**：多套裝標記不僅可讓您向全域報表套裝傳送影像要求，也可傳送給個別子報表套裝。 所有報表套裝中都會針對全域報表資料進行重複資料刪除。

  例如，您可以收集一個全域報表套裝中的所有資料，也可根據品牌、地區或其他區別條件來設定次要報表套裝。 貴公司的不同團隊可能會聚焦於報表套裝中與其相關的資料。

  若要使用多套裝標記，請實作子報表套裝以及包含子報表套裝中的所有資料的全域報表套裝。 您網頁和應用程式的追蹤代碼將包含全域報表套裝的報表套裝 ID (RSID) 以及適用的子報表套裝的 RSID。<!-- Wording/be more specific? And include any links? -->

  影像要求中會針對每個報表套裝發出個別伺服器呼叫。 對子報表套裝的呼叫為次要呼叫。

* **虛擬報表套裝**：[虛擬報表套裝](/help/components/vrs/vrs-about.md)是對全域報表套裝中所收集的指定區段的查詢，可提供給指定的使用者群組使用。 虛擬報表套裝可讓您為不同的一般用戶組織報表元素，而不需要使用多套裝標記，所以可避免次要伺服器呼叫。

  若要使用虛擬報表套裝，請實作全域報表套裝，然後剖析資料來建立已套用特定區段並包含特定群組權限的虛擬報表套裝。 您可以在虛擬報表套裝管理員 ([!UICONTROL 元件] > [!UICONTROL 虛擬報表套裝]) 中建立虛擬報表套裝。 如需詳細資訊，請參閱「[虛擬報表套裝工作流程](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)」。

使用虛擬報表套裝來取代多套裝標記通常是最佳做法，但虛擬報表套裝有一些限制。 請參閱「[虛擬報表套裝和多套裝標記考量事項](/help/components/vrs/vrs-considerations.md)」，以判斷哪一種報表套裝做法是符合貴公司需求的最佳選擇。 如需虛擬報表套裝與多套裝標籤功能的深入比較，請參閱[虛擬報表套裝和多套裝標籤的比較](/help/components/vrs/vrs-about.md)。

<!---## Rollup reports

>[!NOTE]
>
>[!DNL Reports & Analytics] is the only tool that supported rollup reports. Reports & Analytics was end-of-lifed on January 17, 2024.

Limitations of Rollup Reports {#limitations-rollups}

* Rollups provide total data, but they do not report individual values in reports. For example, eVar1 values are not included, but their aggregate total can be.
* Data is not deduplicated when the rollup combines data across report suites.
* Rollups run nightly at midnight.
* When you add a report suite to an existing rollup, historical data is not included in the rollup.
* All child report suites must have data in them for a rollup to function. If new report suites are included in a rollup, make sure to send at least one page view to each of those report suites.
* Rollup report suites can include a maximum of 40 child report suites.
* Rollup report suites can include a maximum of 100 events.
* Data contained in rollup report suites does not support breakdowns or segments.
* The Pages report is replaced with the Most Popular Sites report, which reports on metrics at the child-suite level.

## Comparison of Global Report Suite and Rollup Report  Features

**Secondary server calls**: Rollups do not incur any additional server calls beyond what a single report suite collects. If your organization uses multi-suite tagging, secondary server calls are made for each additional report suite included in an image request.

>[!TIP]
>
>If you use only a global report suite with [virtual report suites](/help/components/vrs/vrs-considerations.md), no secondary server calls are needed.

**Implementation changes**: Rollups do not require any implementation changes, while global report suites require you to include the global report suite ID in your implementation.

**Duplication**: Global report suites deduplicate unique visitors, while rollups do not. For example, if a user visits three of your domains in the same day, rollups would count three daily unique visitors. Global report suites would record one unique visitor.

**Time frame**: Rollups are only processed at midnight each night, while global report suites report data with standard latency.

**Breadth**: Rollups have no way to communicate between report suites. Global report suites can attribute credit to conversion variables between report suites and provide pathing across report suites.

**Historical data**: Rollups can aggregate historical data, while global report suites only report data from the point they were implemented.

**Reports**: Global report suites provide data on all dimensions; rollups provide aggregate data on only high-level reports.

**Supported products**: Rollups could only be used in Reports & Analytics. They are not supported in Analysis Workspace, or Data Warehouse. Global report suites can be used across all products.

**Number of aggregated report suites**: Rollups only support a maximum of 40 child report suites. Global report suites can be implemented on any number of domains or apps that you own.--->
