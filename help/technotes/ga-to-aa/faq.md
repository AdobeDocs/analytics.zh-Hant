---
title: 遷移至 Adobe Analytics 的常見問題集
description: 取得從第三方平台移動至 Adobe 時的常見問題解答。
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: 58d53d6013abcd7d99f2c3cb640d6a648a4ef360
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 53%

---

# 遷移至 Adobe Analytics 的常見問題集

**如何將我的歷史資料從第三方平台移轉至 Adobe Analytics？**

每個 Analytics 平台都有不同的資料收集、處理和儲存方式。Adobe 建議您不要移轉歷史資料，而應建立明確的截止日期，以開始在 Adobe Analytics 內收集和使用資料。會計年度的一開始、日曆年度的一開始或日曆月份的一開始，都是經常使用的截止日期。如果使用者想要檢視歷史資料，可登入第三方平台以取得任何特定的歷史報表需求。

如果貴組織堅持要將歷史資料移轉到Adobe，請聯絡您的Adobe客戶團隊。 實作顧問可與貴組織合作，將 Google Analytics 資料匯出轉譯為 Adobe 資料收集伺服器可內嵌的資料來源。

若要移動歷史資料，建議使用[Customer Journey Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-overview)，它可以帶入任何全頻道資料來源。

**我已經習慣經常在報表中看到分段下拉式清單。 如何在 [!UICONTROL Analysis Workspace] 中加以重新建立？**

下拉式篩選器是[!UICONTROL Analysis Workspace]中一項彈性且強大的功能，可允許區段下拉式清單。 在工作區專案中：

1. 在您要納入下拉式篩選器的元件上使用&#x200B;***ctrl***+***按一下*** (Windows)或&#x200B;***cmd***+***按一下*** (Mac)。 這不僅適用於區段。 任何元件皆可包含在下拉式篩選器中。
2. 將元件群組拖曳至標示為&#x200B;*將區段放置在此處*&#x200B;的工作區區域。 放手前，請按住&#x200B;**[!UICONTROL Shift]**。

存取此[!UICONTROL Workspace]專案的使用者現在可以使用此下拉式篩選器，將區段或其他元件套用至專案。 如需詳細資訊，請參閱 Adobe Analytics 工具指南中的[面板概觀](/help/analyze/analysis-workspace/c-panels/panels.md)。

**我習慣按一下維度項目來查看深入分析。我該如何在 Analysis Workspace 中重現這樣簡單的工作流程？**

[!UICONTROL Analysis Workspace] 中的維度項目也有簡單的劃分工作流程。使用維度專案上的內容功能表來存取劃分。 然後選取&#x200B;**[!UICONTROL 劃分]**，以及所需的元件。 您可以對每個值使用&#x200B;***ctrl***+***select*** (Windows)或&#x200B;***cmd***+***select*** (Mac)，將相同的劃分套用至多個維度專案。
