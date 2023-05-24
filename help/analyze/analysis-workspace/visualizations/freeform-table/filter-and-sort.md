---
description: 描述 Analysis Workspace 如何篩選及排序表格的文件。
title: 篩選和排序表格
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: 602f837689186f232c4c0f8baebbcf911446bc99
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 76%

---

# 篩選和排序表格

Analysis Workspace 中的自由表格是互動式資料分析的基礎。因此，它們可包含數千列資訊。若要有效地展示最重要的資訊，對資料進行篩選和排序相當重要。

## 篩選表格

Analysis Workspace 中的篩選器可協助您找出最重要的資訊。

>[!NOTE]
>
> 只能按本節所述篩選動態尺寸項。 無法篩選靜態維度項。 有關詳細資訊，請參見 [自由形式表中的動態尺寸項與靜態尺寸項](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。

### 快速從表中排除特定行

您可以快速從表中排除特定行，而無需開啟「篩選器」對話框。

>[!NOTE]
>
>如本節所述排除行時， [!UICONTROL **始終排除項**] 規則將自動應用於高級篩選器對話框。 (通過選擇「篩選器」表徵圖，然後 [**[!UICONTROL 顯示高級]**](#apply-a-simple-or-advanced-filter-to-a-table)。)

要快速從自由形式表中排除特定行：

1. 將滑鼠懸停在要排除的行上，然後選擇x表徵圖。

   按住Shift鍵選擇範圍行，或按住Command鍵(在Mac)或Ctrl鍵（在Windows上）選擇多行。

### 將簡單或高級篩選器應用於表

若要篩選自由表格中的資料：

1. 將滑鼠懸停在包含要篩選的資料的列上。 <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. 選取出現的&#x200B;**篩選**&#x200B;圖示。

   ![表格中的篩選器圖示](assets/table-filter-icon.png)

   提供下列選項：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **搜索詞或短語**] | 指定要篩選依據的字詞或短語。 只顯示包含指定字詞或確切片語的行。 |
   | [!UICONTROL **包含未指定 (無)**] | 選擇此選項可在表格中顯示不屬於任何表格維度的資料。<!--what is this?--> |

1. (選用) 若要依不同條件或依多個條件篩選，請選取&#x200B;[!UICONTROL **顯示進階**]。

   以下高級篩選器選項可用：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **包含未指定 (無)**] | 選擇此選項可在表格中顯示不屬於任何表格維度的資料。<!--what is this?--> |
   | [!UICONTROL **符合**] | <p>選擇&#x200B;[!UICONTROL **如果滿足所有條件**]&#x200B;即可僅顯示符合您指定之所有條件的資料。 此選項通常會產生更精細的資料。</p> <p>選擇&#x200B;[!UICONTROL **如果符合任何條件**]&#x200B;即可顯示符合您指定之任何篩選條件的資料。 此選項通常會產生較少精細的資料。</p> |
   | [!UICONTROL **標準**] | <p>從下列篩選選項中選取：</p><p>(選擇&#x200B;[!UICONTROL **新增列**]&#x200B;新增多個篩選條件。 您在&#x200B;[!UICONTROL **符合**]&#x200B;區段選擇的選項決定是否必須滿足您新增的全部或任何條件。)</p><ul><li><p>[!UICONTROL **包含片語**]：篩選結果中只會包含您指定之確切片語的資料。 字詞必須按照&#x200B;[!UICONTROL **搜尋字詞或片語欄位**]&#x200B;中指定的順序排列。<p>這是執行簡單搜尋時的預設設定。</p></p></li><li><p>[!UICONTROL **包含任何詞語**]：篩選結果中只會包含來自您所指定片語的一或多個字詞。 </p></li><li><p>[!UICONTROL **包含所有詞語**]：篩選結果中只會包含來自您所指定片語的所有字詞的資料。字詞不必按照&#x200B;[!UICONTROL **搜尋字詞或片語欄位**]&#x200B;中指定的順序排列。</p></li><li><p>[!UICONTROL **不包含任何詞語**]：篩選結果中只會顯示不含您所指定片語的一或多個字詞。 </p></li><li><p>[!UICONTROL **不包含片語**]：篩選結果中只會顯示不含您指定之確切片語的資料。 字詞必須按照&#x200B;[!UICONTROL **搜尋字詞或片語欄位**]&#x200B;中指定的順序排列。</p></li><li><p>[!UICONTROL **等於**]：篩選結果中只會包含與您所指定之片語完全相符的資料。 </p></li><li><p>[!UICONTROL **不等於**]：篩選結果中只會包含與您所指定之片語不完全相符的資料。 </p></li><li><p>[!UICONTROL **開頭為**]：篩選結果中只會包含以您指定的字詞或確切片語開頭的資料。 </p></li><li><p>[!UICONTROL **結尾為**]：篩選結果中只會包含以您指定的字詞或確切片語結尾的資料。 </p></li></ul> |
   | [!UICONTROL **永遠排除項目**] | 指定要從篩選資料中排除的任何項目的名稱。 |

1. 選擇&#x200B;[!UICONTROL **套用**]&#x200B;以篩選資料。

   在將篩選器套用至表格時，此&#x200B;**篩選器**&#x200B;圖示![藍色篩選器圖示篩選表格](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)會變成藍色。

## 排序表格

您可以依照 Analysis Workspace 中屬於量度的任何欄，來排序自由格式表格的資料。

向下箭頭圖示![向下箭頭圖示排序表格欄](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg)會顯示在目前依資料排序的欄標題中。

若要按特定欄排序自由格式表格中的資料：

1. 請將滑鼠懸停在要作為資料排序依據的欄標題上。

2. 選取出現的向下箭頭圖示。

   ![向下箭頭圖示排序表格欄](assets/table-sort.png)

   表格資料會按您選擇的欄排序。
