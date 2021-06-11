---
description: 了解如何實作多套裝標籤，以傳送影像要求至多個報表套裝。
title: 實作多套裝標籤
exl-id: null
source-git-commit: 81da9ff9b00a69c49c028fc7f006c161d8ff21d4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 3%

---


# 實作多套裝標籤

[多套裝標](/help/admin/c-manage-report-suites/rollup-report-suite.md) 記不僅可讓您傳送影像要求至全域報表套裝，也可傳送至個別子報表套裝，讓您能將公司全域報表套裝資料的子集提供給不同的使用者。

若要實作多套裝標籤，您必須在網頁和應用程式的追蹤程式碼中包含全域報表套裝的報表套裝ID(RSID)，以及適用子報表套裝的RSID。

* 針對Adobe Experience Platform Launch實作，請指定[[!DNL Analytics] extension](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html?lang=zh-Hant)的每個報表套裝。

* 對於舊版JavaScript和行動SDK實作，請以逗號和空格（`rsid1,rsid2,rsid3`等）分隔RSID。

* 對於其他實作類型，請使用必要語法來列出多個RSID。

>[!TIP]
>
> 最佳作法是先列出全域報表套裝或報表套裝ID。

多套裝標籤會針對每個影像要求產生多個伺服器呼叫：對全域報表套裝的主要呼叫，以及每個子報表套裝的次要呼叫。

>[!NOTE]
>
> [虛擬報表套裝](/help/components/vrs/vrs-about.md)（也可讓您為不同的使用者提供公司全域報表套裝資料的子集）不會產生次要伺服器呼叫。

## 我應實作多套裝標籤或虛擬報表套裝？

使用虛擬報表套裝而非多套裝標籤通常是最佳作法，但業務需求會決定適合貴組織的最佳報表套裝方法。

若要了解虛擬報表套裝是否是您的最佳方法，請參閱「[虛擬報表套裝和多套裝標籤考量事項](/help/components/vrs/vrs-considerations.md)」。 如需多套裝標籤與虛擬報表套裝功能的比較，另請參閱「[虛擬報表套裝與多套裝標籤](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)」。
