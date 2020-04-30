---
description: 虛擬報表套裝可在 Analysis Workspace 中進行管理，以包含和排除元件。
title: 虛擬報表套裝元件管理
uuid: 6c6a4071-22ad-4e8c-b1ed-140b2aa04f76
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# 虛擬報表套裝元件管理

虛擬報表套裝可在 Analysis Workspace 中進行管理，以包含和排除元件。

>[!NOTE]管理員與非管理員可在已組織的 Workspace 專案和虛擬報表套裝 (VRS) 中查看的元件有所變動。以前，任何人只要按一下，就能看到未組織的元件 **[!UICONTROL Show all Components]**。 [更新的組織體驗](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html)能讓您對可查看的元件執行更細微的控制。

啟用元件管理：

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]** > **[!UICONTROL Create new virtual report suite]**.
1. 定義後， **[!UICONTROL Settings]**&#x200B;按一下該選 **[!UICONTROL Components]** 項卡。

1. 選中複選框 **[!UICONTROL Enable Customization of Virtual Report Suite Components]**:

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >如已啟用元件自訂，則&#x200B;**只能在 Analysis Workspace 中**&#x200B;存取虛擬報表套裝，且無法在以下項目中存取：

   * [!UICONTROL Reports & Analytics]
   * [!UICONTROL Ad Hoc Analysis]
   * [!UICONTROL Data Warehouse]
   * [!UICONTROL Report Builder]
   * Analytics 報表 API
   勾選後，只要從「已排除元件」欄將相關的元件拖曳到「已包含元件」欄，即可新增要包含在虛擬報表套裝的元件。可包含和排除的元件有：

   * 維度
   * 量度
   * 區段
   * 日期範圍
   >[!NOTE]
   >
   >不需要&#x200B;*共用*&#x200B;已組織的元件 (區段、計算量度、日期範圍)。只要元件是針對虛擬報表套裝而進行管理，即使不共用，也會一律顯示在 Analysis Workspace 中。

1. Additionally, you can filter or search the components and add the entire filtered selection to the included column by clicking **[!UICONTROL Add All]**.

   ![](assets/vrs-add-all.png)

## 重新命名元件 {#section_0F7CD9F684FE4765BC00A2AFED56550E}

您可以對虛擬報表套裝變更已包含元件的顯示名稱。例如，若您想在虛擬報表套裝中包含「頁面名稱」，但想將其重新命名為更適合行動裝置使用的環境，您可以將名稱變更為「應用程式畫面」。任何時候，只要使用這個虛擬報表套裝，Analysis Workspace 都會顯示新名稱。

![](assets/vrs-rename-component.png)

在 Analysis Workspace 中，按一下任何已包含元件的資訊圖示，以顯示已重新命名元件的原始名稱:

![](assets/vrs-aw-renamed.png)

## 元件群組 {#section_483BEC76F49E46ADAAA03F0A12E48426}

使用元件群組對虛擬報表套裝進行大量元件新增作業。例如，若您想匯入專屬行動應用程式分析的預設元件集，請選取行動應用程式群組。對應的維度和量度集 (已重新命名) 會自動新增到虛擬報表套裝的「己包含」清單中。

![](assets/vrs-comp-grp.png)

## 工作區行為 {#section_6C32F8B642804C0097FCB14E21028D4A}

如需有關在 Analysis Workspace 中進行管理的詳細資訊，請參閱[組織和共用專案](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/curate-share/curate.html)。
