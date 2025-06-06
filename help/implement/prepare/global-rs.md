---
title: Adobe Analytics 中的全域報表套裝
description: 瞭解使用全域報表套裝的優點和需求。
feature: Implementation Basics
exl-id: fa949b1e-80bd-41cf-a294-c840503b568f
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 100%

---

# 全域報表套裝考量事項

全域報表套裝是一種可從您組織擁有的所有網域和應用程式中收集資料的報表套裝。這項資料收集技術需要準備工作，而且需要組織內各團隊的彼此協調。

## 優勢

Adobe 建議您在多數情況下都實施全域報表套裝。

* **匯整資料：**&#x200B;全域報表套裝可讓您查看自家網站中的 KPI 和成功事件。區段和虛擬報表套裝可用來檢視網站特定資料。
* **支援跨裝置分析：** CDA 需要採用從多個位置 (例如您的網站和行動應用程式) 收集資料的報表套裝。只要實施正確，個別裝置的資料就能串連起來。如需詳細資訊，請參閱元件使用指南中的[跨裝置分析](../../components/cda/overview.md)。
* **不需要多個報表套裝：**&#x200B;所有資料都可在單一報表套裝中收集，因此得以降低開發人員誤將資料傳送至錯誤報表套裝的機率。
* **無需統計：**&#x200B;統計是推出相當久的功能，每日都會彙總個別報表套裝的資料。統計功能不會去除重複的造訪或訪客資料，因此可能導致數據膨脹。如需詳細資訊 ，請參閱管理員使用指南中的[統計](../../admin/admin/c-manage-report-suites/rollup-report-suite.md)。
* **節省時間：** Workspace 專案、分類、區段和計算量度都與相同的全域報表套裝連結。管理員管理這些元件和資料控管的時間得以減少。
* **更精確的跨品牌歸因：**&#x200B;如果造訪從某個網站開始，接著您的另一個網站在觸發成功事件之前又發生點擊，系統會精確收集到歸因資料。舉例來說，訪客點擊付費搜尋連結並到達網站 A，接著又按一下網站 B 的連結，然後才進行購買。全域報表套裝可正確回頭將該次購買歸給付費搜尋。
* **簡化實作：**&#x200B;由於所有品牌/網站都會將資料傳送至相同的報表套裝，因此每個網站的實作都會保持一致。這項強制的控管方式可確保特定維度或量度都儲存在相同的 eVar 或事件中。透過這項簡化措施，管理員、測試者、標記管理負責人和分析師都能獲益。

>[!NOTE]
>
> 協調全域報表套裝實作是一項浩大的工程。Adobe 建議您與顧問合作，減少工作產生的複雜性和問題。

## 使用全域報表套裝啟動新實作

請使用下列一般準則來瞭解實施全域報表套裝的程序。

1. 在 Adobe Analytics 中建立全域報表套裝。如需詳細資訊，請參閱管理員使用指南中的[建立報表套裝](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)。
1. 與組織中負責每個網域的團隊合作。多數團隊都有其業務領域特定的報表需求。
1. 您可以在[解決方案設計文件](solution-design.md)中記錄並彙總所有這些需求。如果不同團隊對某個維度有類似需求，就可使用相同的自訂變數。舉例來說，如果網站 A 和網站 B 都需要階層連結維度，則兩個網站的實作都可透過 eVar1 傳送該項資料。

   >[!IMPORTANT]
   >
   > 請確認您在不同網域間使用任何指定自訂變數的方式都相同。如果不同網站的用途不同，請勿使用相同的 eVar 或事件。
1. 請確認每個網域都有資料層，以便簡化資料收集。沒有資料層依然可以收集資料，但實作的可靠性和持久性會降低，尤其當您的網站經過重新設計時更是如此。
1. 使用 Adobe Experience Platform 中的標記來實作 Analytics。 不同的網站可能需要不同的資料元素。使用每個網域的特定規則，才能確保每個資料元素皆正確填入，並且這些資料元素能夠指派給各自對應的 eVar 和事件。請參閱「[標記總覽](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hant)」。
1. 納入 [Adobe Experience Cloud ID Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)，並使用 [appendVisitorIDsTo](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/appendvisitorid.html?lang=zh-Hant) 函數。使用者從一個網域點點擊前往另一個網域時，此函數會合併這些訪客資料。

## 使用全域報表套裝修改現有實作

將多個網站的現有實作項目移至單一全域報表套裝的程序，需要組織中的團隊付出更多時間與協調。

1. 您可以決定要使用任一個現有報表套裝，還是以新的報表套裝從零開始。如果您想要變更實作中現有變數的使用情形，建議從新的報表套裝開始。
2. 決定您要切換至全域報表套裝的轉換日期。轉換的最佳時機是兩次重要報表期之間，或者網站進行重大變更的同時。會計季度或會計年度之初、網站重新整理期間，或新標記管理系統進行變更，都是轉換的好時機。
3. 請按照上述步驟進行 (建立報表套裝、在解決方案設計文件中整理出報表需求，並在每個網站上建立資料層)。在實作 Adobe Experience Platform 中的標記時，請使用您網站的開發版本來驗證您的實作。
4. 在確認您的實作可在開發環境中使用後，請在轉換日期將您的標記實作推送到線上。

## 相關頁面

[從多套裝標記移至全域報表套裝和虛擬報表套裝](../../components/vrs/vrs-considerations.md)
[比較統計和全域報表套裝](../../admin/admin/c-manage-report-suites/rollup-report-suite.md)
