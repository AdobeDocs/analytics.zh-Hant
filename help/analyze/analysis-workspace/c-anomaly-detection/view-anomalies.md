---
description: 您可以在表格或線性圖中檢視異常。
title: 在 Analysis Workspace 中檢視異常
feature: Anomaly Detection
role: User, Admin
exl-id: 32edc7f4-c9b9-472a-b328-246ea5b54d07
source-git-commit: 984406d00e5a5ae966fff60ec9fcfcb000958696
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 100%

---

# 在 Analysis Workspace 中檢視異常

您可以在表格或線性圖中檢視異常。

## 在表格中檢視異常 {#section_869A87B92B574A38B017A980ED8A29C5}

您可以在時間序列自由表格中檢視異常。

1. 在欄標題中選取欄設定圖示，然後確定選項清單中已選取&#x200B;[!UICONTROL **「異常」**]&#x200B;選項。 如需詳細資訊，請參閱[欄設定](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)。

1. 按一下離開設定選單以檢視更新的表格。

   ![](assets/anomaly_detected.png)

1. 異常情況在表格中顯示如下：

   **深灰色三角形**&#x200B;會顯示在偵測到資料異常的每一列的右上角。

   每一列中的彩色&#x200B;**垂直線**&#x200B;則表示預期值。每一列中的彩色&#x200B;**陰影區域**&#x200B;則表示實際值。線條 (預期值) 與陰影區域 (實際值) 的比較方式會決定是否有異常。 (根據[異常偵測所使用的統計技術](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)中所述的進階統計技術，觀察被視為異常。)

1. 選取列右上角的灰色三角形，以檢視異常的詳細資訊。 這會顯示實際值高於或低於預期值的偏離程度 (以百分比表示)。

## 在線性圖中檢視異常 {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

折線圖是唯一可讓您檢視異常的視覺效果。

若要在折線圖中檢視異常：

1. 在視覺效果標題中選取設定圖示，然後確定選項清單中已選取&#x200B;[!UICONTROL **「顯示異常」**]&#x200B;選項。如需詳細資訊，請參閱[折線圖](/help/analyze/analysis-workspace/visualizations/line.md)。

1. (可選) 若要允許信賴區間縮放圖表，請選取視覺效果標題中的設定圖示，然後選取&#x200B;**[!UICONTROL 「允許異常縮放 Y 軸」]**&#x200B;選項。

   預設為不選取此選項，因為有時會讓圖表較不清晰。

1. 按一下離開設定選單以檢視更新的折線圖。

   ![](assets/anomaly_linechart.png)

   異常情況在折線圖中顯示如下：

   **白點**&#x200B;會顯示在偵測到資料異常的位置。(根據[異常偵測所使用的統計技術](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)中所述的進階統計技術，觀察被視為異常。)

   此&#x200B;**淺色陰影區域**&#x200B;是信賴範圍或預期範圍，值應發生的位置。任何超出此預期範圍的值都是異常。

   如果折線圖中有多個量度，系統只會顯示異常值，您必須將滑鼠移到每個異常值上方，才能查看該量度的信賴帶。

   此&#x200B;**虛線**&#x200B;是確切的預期值。

1. 按一下異常 (白點) 即可檢視下列資訊：

   * 異常發生的日期

   * 異常情形的原始值

   * 高於或低於期望值的百分比，期望值會加上綠色實線。

   * 啟動貢獻分析的分析連結

     (如需詳細資訊，請參閱[異常偵測概觀](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)。)





