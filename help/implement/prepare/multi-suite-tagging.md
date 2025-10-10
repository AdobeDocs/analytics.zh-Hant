---
description: 了解如何實作多套裝標記，以傳送影像要求給多個報表套裝。
title: 實作多套裝標記
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
role: Admin, Developer, Leader
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 93%

---

# 實作多套裝標記

[多套裝標記](/help/admin/tools/manage-rs/rollup-report-suite.md)不僅可讓您向全域報表套裝傳送影像要求，也可傳送給個別子報表套裝，好讓您可以將貴公司的部分全域報表套裝資料傳送給不同一般使用者。

若要實作多套裝標記，您必須在您網頁和應用程式的追蹤程式碼中，加入全域報表套裝的報表套裝 ID (RSID)，也要加入適用的子報表套裝的 RSID。

* 針對 Adobe Experience Platform 標記實作，請為[[!DNL Analytics] 擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=zh-Hant)指定每個報表套裝。

* 若要舊版 JavaScript 和行動 SDK 實作，請用逗號且不含空格來區隔 RSID (`rsid1,rsid2,rsid3` 等)。

* 若為其他實作類型，請使用列出多個 RSID 所需的語法。

>[!TIP]
>
> 最佳做法是先列出全域報表套裝或報表套裝 ID。

多套裝標記會導致每個影像要求有多個伺服器呼叫：對全域報表套裝發出主要要求，並對每個子報表套裝發出次要要求。

>[!NOTE]
>
> [虛擬報表套裝](/help/components/vrs/vrs-about.md)，可讓您將貴公司的部分全域報表套裝資料提供給不同一般使用者，而不會產生次要伺服器呼叫。

## 我應該實作多套裝標記還是虛擬報表套裝？

使用虛擬報表套裝來取代多套裝標記通常是最佳做法，但您的業務需求會決定最適合貴組織的報表套裝做法。

若要了解虛擬報表套裝是否為最佳做法，請參閱「[虛擬報表套裝和多套裝標記考量事項](/help/components/vrs/vrs-considerations.md)」。 另請參閱&quot;[虛擬報表套裝與，多套裝標籤](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot;，以取得多套裝標籤與虛擬報表套裝功能的比較。
