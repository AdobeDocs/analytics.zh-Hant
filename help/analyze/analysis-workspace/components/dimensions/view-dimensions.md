---
description: 瞭解如何在Analysis Workspace中檢視詳細資料和維度的最高值。
title: 預覽維度
feature: Dimensions
role: User, Admin
exl-id: 897edc76-6744-4d8c-ab0e-20672838f7b3
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 4%

---

# 預覽維度

您可以使用元件的[元件資訊](/help/analyze/analysis-workspace/components/use-components-in-workspace.md#component-info)來顯示維度的排名最前的專案。

![元件資訊](assets/component-info.png)

<!--
Now, by default, we show dynamic values instead of static ones, with the option to turn them into static values. Other things to note:

* As your data updates, the dynamic dimension columns will update to show the current 5/15 dimension items.
* A dynamic dimension column that is copied or moved will become static.
* When hovering a static dimension column you will see a lock icon, indicating that the dimension is static.

![Dimension column popup highlighting the lock icon.](assets/dimension_static.png)

-->


## 顯示維度項目

當您在元件面板中為維度選取![V形右側](/help/assets/icons/ChevronRight.svg)時，會顯示其維度專案清單。 維度專案清單通常會顯示過去30天排名最前的專案。 當更多專案可供使用時，在面板的所選日期範圍之外，選取連結以顯示更多專案。 例如，**[!UICONTROL 顯示上個月]**&#x200B;的專案。

![顯示維度專案](assets/dimension-items.png)


<!--
# Preview dimensions

Hover over the information (i) icon next to a dimension. This shows the top 5 values for non-time dimensions (and 15 for time dimensions). We used to keep those values static (i.e., the 5 values picked never changed).

![](assets/dimension-preview.png)

Now, by default, we show dynamic values instead of static ones, with the option to turn them into static values. Other things to note:

* As your data updates, the dynamic dimension columns will update to show the current 5/15 dimension items.
* A dynamic dimension column that is copied or moved will become static.
* When hovering a static dimension column you will see a lock icon, indicating that the dimension is static.

![](assets/dimension_static.png)

## Show dimension items

When you hover over a dimension and click the grey right-arrow next to it, a list of its dimension items appears. Any list of dimension items usually shows the top items for the last 30 days.

If you scroll down to the bottom of the list, you see **[!UICONTROL Show Top Items From Last 18 Months]**. Click this option to see top dimension items from the last 547 days.

-->
