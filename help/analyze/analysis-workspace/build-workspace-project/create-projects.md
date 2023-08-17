---
description: 瞭解在Analysis Workspace中建立專案的基本知識
title: 建立專案
feature: Workspace Basics
role: User, Admin
exl-id: 6130b1d8-078c-46d8-9fce-eb39739a9570
source-git-commit: fabe043264e4567d54dc497897fff0aaad77eaaf
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 14%

---

# 在Analysis Workspace中建立專案

[專案](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) Analysis Workspace可讓您檢視與組織內部或外部利害關係人共用的業務關鍵型分析。

如需如何開始使用Analysis Workspace的一般資訊，請參閱 [Analysis Workspace概觀](/help/analyze/analysis-workspace/home.md).

以下章節說明如何建立專案，並開始新增任何Analysis Workspace專案的關鍵建置區塊：面板、視覺效果和元件。

## 從空白專案或報告建立專案

1. 在Adobe Analytics中，選取 [!UICONTROL **工作區**].

1. 選擇是要建立空白專案，還是從報表建立專案：

   +++建立空白專案

   1. 在 [!UICONTROL **工作區**] 索引標籤中，選取 [!UICONTROL **專案**] 標籤填入頁面左側，然後選取 [!UICONTROL **建立專案**].

   1. 選擇建立空白專案或空白行動計分卡

      * **空白專案** 如果您打算從瀏覽器共用分析
      * [**空白行動計分卡**](/help/analyze/mobile-app/curator.md) 如果您打算從Adobe Analytics儀表板行動應用程式共用分析。

   1. 選擇 [!UICONTROL **建立**]。

+++

   +++從報告建立專案

   1. 在 [!UICONTROL **工作區**] 索引標籤中，選取 [!UICONTROL **報表**] 標籤填入頁面左側。

   1. 搜尋或導覽至您要使用的報表，然後在其出現時選取它。

      預設提供一組標準報表。 此外，貴組織可能已建立自訂報表供您選擇。

   1. 選取 [!UICONTROL **專案**] > [!UICONTROL **儲存**] 將報表另存為新專案。

      如需關於報告的詳細資訊，請參閱以下的「瀏覽報告索引標籤」： [Adobe Analytics登陸頁面](/help/analyze/landing.md).

+++

1. 接下來，您需要將面板、視覺效果和元件新增至專案。 首先，在Analysis Workspace中新增面板至您的專案，如所述 [將面板新增至專案](#add-panels-to-the-project). 然後您可以在任何面板中新增視覺效果。 最後，您可以將元件新增至任何面板或視覺效果。

## 將面板新增至專案 {#panels}

[面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) 是Analysis Workspace中任何專案的基礎。 面板是用來組織專案的內容（視覺效果和元件）。

Analysis Workspace 中提供的許多面板皆可根據用戶輸入的少量內容，產生完整的分析集。

若要新增面板：

1. 選取 [!UICONTROL **面板**] 圖示加以搜尋。

   ![](assets/build-panels.png)

1. 搜尋您要新增的面板。 當它出現在左側邊欄中時，請將它拖曳到您的專案中。

1. 將視覺效果新增至面板，如所述 [將視覺效果新增至專案](#add-visualizations-to-the-project).

   或者，您也可以將元件直接新增至面板，如中所述 [將元件新增至專案](#add-components-to-the-project).

## 將視覺效果新增至專案

[視覺效果](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) （例如自由表格、長條圖或折線圖）能以視覺化方式呈現資料。

>[!TIP]
>
>自由表格是最常見的視覺效果型別，也是互動式資料分析的基礎。 如需如何在Analysis Workspace中使用自由格式表格的詳細資訊，請參閱 [自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md).

若要新增視覺效果：

1. 選取 **[!UICONTROL 視覺效果]** 圖示加以搜尋。

   ![](assets/build-visualizations.png)

1. 搜尋您要新增的視覺效果。 當它出現在左側邊欄中時，請將它拖曳至專案內的面板。

1. 將元件新增至視覺效果，如所述 [將元件新增至專案](#add-components-to-the-project).

## 將元件新增至專案

[元件](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) 構成任何專案的實際資料。 您可以將元件新增至視覺效果或面板。

>[!TIP]
>
>如需每個元件的詳細資訊，請在左側邊欄中選取元件名稱旁的「資訊」圖示，或參閱 [Analytics元件指南](/help/components/home.md).

若要新增元件：

1. 選取 **[!UICONTROL 元件]** 圖示加以搜尋。

   ![](assets/build-components.png)

1. 搜尋您要新增的元件。 當它出現在左側邊欄中時，請將它拖曳至專案中的面板或視覺效果。

1. （選用）共用專案，如所述 [儲存並共用專案](#save-and-share-the-project).

## 儲存並共用專案

您在 Analysis Workspace 中建立分析時，您的工作會[自動儲存](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)。

完成專案建置並開始收集可操作分析時，該專案就可供其他人使用。您可以與組織中的使用者和群組 (或甚至組織外部的人員) 共用該專案。如需有關共用專案的資訊，請參閱[共用專案](/help/analyze/analysis-workspace/curate-share/share-projects.md)。
