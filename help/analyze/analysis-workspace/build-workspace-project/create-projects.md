---
description: 了解在 Analysis Workspace 中建立專案的基本知識
title: 建立專案
feature: Workspace Basics
role: User, Admin
exl-id: 24193013-1361-43fc-b129-c44f207d9101
source-git-commit: 273fea86cde8880d9c9e03ac9c6a99b75f70f6cd
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 100%

---

# 在 Analysis Workspace 中建立專案

Analysis Workspace 中的[專案](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)可讓您檢視可與組織內部或外部利害關係人共用的關鍵業務分析。

如需有關如何開始使用 Analysis Workspace 的一般資訊，請參閱「[Analysis Workspace 概觀](/help/analyze/analysis-workspace/home.md)」。

以下小節將說明如何建立專案，以及如何為任何 Analysis Workspace 專案開始新增關鍵建置區塊：面板、視覺效果和元件。

## 使用空白專案或報告建立專案

1. 在 Adobe Analytics 中，選取「[!UICONTROL **Workspace**]」。

1. 選擇要建立空白專案或使用報告建立專案：

   +++建立空白專案

   1. 在「[!UICONTROL **Workspace**]」標籤上，選取頁面左側的「[!UICONTROL **專案**]」標籤，然後選取「[!UICONTROL **建立專案**]」。

   1. 選擇要建立空白專案或行動計分卡

      * 如果您打算從瀏覽器共用分析，請建立&#x200B;**空白專案**
      * 如果您打算從 Adobe Analytics 儀表板行動應用程式共用分析，請建立&#x200B;[**空白行動計分卡**](/help/analyze/mobile-app/curator.md)。

   1. 選取「[!UICONTROL **建立**]」。

+++

   +++使用報告建立專案

   1. 在 [!UICONTROL **Workspace**] 標籤中，選取頁面側的「[!UICONTROL **報告**]」標籤。

   1. 搜尋或導覽至您要使用的報告，然後在顯示時選取。

      依預設提供一組標準報告。此外，您的組織可能已建立自訂報告供您選擇。

   1. 選取「[!UICONTROL **專案**] > [!UICONTROL **儲存**]」，將報告儲存為新專案。

      如需報告的詳細資訊，請參閱 [Adobe Analytics 登陸頁面](/help/analyze/landing.md)中的「導覽至報告標籤」。

+++

1. 接下來，您需要為專案新增面板、視覺效果和元件。首先，將面板新增到 Analysis Workspace 中的專案，如[將面板新增到專案](#add-panels-to-the-project)中所述。接著，您可以將視覺效果新增到任何面板。最後，您可以將元件新增到任何面板或視覺效果。

## 將面板新增到專案 {#panels}

[面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)是 Analysis Workspace 中任何專案的基礎。面板是用來組織專案的內容 (視覺效果和元件)。

Analysis Workspace 中提供的許多面板皆可根據用戶輸入的少量內容，產生完整的分析集。

若要新增面板：

1. 選取左側邊欄中的「[!UICONTROL **面板**]」圖示。

   ![](assets/build-panels.png)

1. 搜尋您要新增的面板。它顯示在左側邊欄時，請將其拖曳到專案中。

1. 將視覺效果新增到面板，如[將視覺效果新增到專案](#add-visualizations-to-the-project)中所述。

   您也可以將元件直接新增到面板，如[將元件新增到專案](#add-components-to-the-project)中所述。

## 將視覺效果新增到專案

[視覺效果](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) (例如自由格式表格、長條圖或折線圖) 可用來生動地呈現資料。

>[!TIP]
>
>自由格式表格是最常見的視覺效果類型，是互動式資料分析的基礎。如需更多有關如何在 Analysis Workspace 中使用自由格式表格的詳細資料，請參閱「[自由格式表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)」。

若要新增視覺效果：

1. 選取左側邊欄中的「**[!UICONTROL 視覺效果]**」圖示。

   ![](assets/build-visualizations.png)

1. 搜尋您要新增的視覺效果。它出現在左側邊欄時，請將其拖曳到專案中的面板中。

1. 將元件新增到視覺效果中，如[將元件新增到專案](#add-components-to-the-project)中所述。

## 將元件新增到專案

[元件](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)會組成任何專案的實際資料。您可以將元件新增到視覺效果或面板。

>[!TIP]
>
>如需有關各個元件的資訊，請選取左側邊欄中元件名稱旁邊的「資訊」圖示，或參閱「[Analytics 元件指南](/help/components/home.md)」。

以下基本資訊說明如何將元件新增至 Analysis Workspace 中的專案。如需進一步瞭解如何新增各種類型的元件 (維度、指標、區段和日期範圍)，請參閱[在 Analysis Workspace 中使用元件](/help/analyze/analysis-workspace/components/use-components-in-workspace.md)。

若要將元件新增至 Analysis Workspace 中的專案：

1. 選取左側邊欄中的「**[!UICONTROL 元件]**」圖示。

   ![](assets/build-components.png)

1. 捲動至或搜尋要新增的元件，然後將其拖曳到專案中的面板或視覺化效果中。

   例如，您可以將區段拖曳到面板標題中的區段放置區域。

   ![將區段放入放置區](assets/segment-dropzone.png)

   有關將元件新增至專案的詳細資訊，請參閱[在 Analysis Workspace 中使用元件](/help/analyze/analysis-workspace/components/use-components-in-workspace.md)。

1. (選用) 依照[儲存和共用專案](#save-and-share-the-project)中所述共用專案。

## 儲存和共用專案

您在 Analysis Workspace 中建立分析時，您的工作會[自動儲存](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)。

完成專案建置並開始收集可操作分析時，該專案就可供其他人使用。您可以與組織中的使用者和群組 (或甚至組織外部的人員) 共用該專案。如需有關共用專案的資訊，請參閱[共用專案](/help/analyze/analysis-workspace/curate-share/share-projects.md)。
