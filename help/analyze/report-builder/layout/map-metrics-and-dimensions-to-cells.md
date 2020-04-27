---
description: 在將項目映射至試算表之前，請確認試算表的保護機制已解除。如果工作表的保護機制禁止任何使用者動作，您將無法選擇試算表中的儲存格。因此，請先解除工作表的保護機制，然後再新增儲存格映射。
title: 將度量和維度映射至儲存格
topic: Report builder
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 將度量和維度映射至儲存格

在將項目映射至試算表之前，請確認試算表的保護機制已解除。如果工作表的保護機制禁止任何使用者動作，您將無法選擇試算表中的儲存格。因此，請先解除工作表的保護機制，然後再新增儲存格映射。

可映射的區域和儲存格數量會隨著選擇的度量、粒度、日期範圍及設定的篩選而改變。例如，如果您選取 [!UICONTROL Site Metric] > [!UICONTROL Traffic Report]、設定詳細程度，並設定日期範圍 [!UICONTROL Week] ，則系統會提示您在上映射三個儲存格(使用時 [!UICONTROL Last 2 Weeks]) [!UICONTROL Custom Layout][!UICONTROL Request Wizard: Step 2]。 請求會擷取第一週的資料和第二週的資料，而每個資料點值 = 頁面檢視的值。Your third cell serves as the row heading, which you can configure using [!UICONTROL Format Options].

當您意外映射試算表中不相容的位置時，Report Builder 會發出錯誤。

以下章節包含更多資訊：

* [選擇儲存格範圍](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [選擇儲存格的技巧](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [映射時發生的問題](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## 選擇儲存格範圍 {#section_1E37FB46DA194FB7A1050B8833A48AC6}

On the [!UICONTROL Request Wizard: Step 2], when you enable [!UICONTROL Custom Layout] for a trended request, you can map the request to a range of cells.

按一 **[!UICONTROL Range Selector]** 下select_ ![cell_icon.png](assets/select_cell_icon.png)

，位於要映射的項目旁。

* **範圍內的所有儲存格：** 要求您為樣式請求選擇一組儲 [!UICONTROL Custom Layout] 存格。
* **範圍的第一個儲存格：** 可讓您選取範圍的左上角儲存格，並顯示方 [!UICONTROL Range] 向以指定輸入和輸出儲存格（欄或列）的水準或垂直方向。 此選項可讓 Report Builder 為您選擇儲存格。
* **範圍方向：**&#x200B;可讓您指定欄或列方向的儲存格範圍。
* **選擇範圍的上方儲存格位置：**&#x200B;顯示儲存格參考。

## 選擇儲存格的技巧 {#section_760421C3D7F84D67A639174710C93B22}

You select the data by clicking the **[!UICONTROL Range Selection]** icon  ![select_cell_icon.png](assets/select_cell_icon.png)

 選擇資料，然後在試算表內按一下滑鼠，並拖曳到需要的儲存格範圍。此時，黑色邊框會勾勒出連續的選擇範圍。

![](assets/twenty_cells.gif)

個別選擇的列在每個列的周圍會有白色的細邊框。

![](assets/twoXten_cells_highlighted.gif)

若要映射一個請求中個別的列，請按住 [!UICONTROL Control] 鍵，然後按一下滑鼠按鍵並將游標拖曳至需要的儲存格。如果請求需要四個各有十個儲存格的區域 (而不是一個含有 40 個儲存格的連續區域)，您便可以使用這項操作。

![](assets/map4.png)

選取儲存格後，再按一 **[!UICONTROL Range Selector]** 下表格上 [!UICONTROL Range Selection] 的，返回至 [!UICONTROL Request Wizard: Step 2]。

## 映射時發生的問題 {#section_CC1BCF841291447EB3A994EB08F3A099}

如果意外選擇映射至已有作用中映射的儲存格，您會發現範圍選取器圖示旁的文字方塊內不會出現儲存格參考。When you click [!UICONTROL OK], report builder displays the error, &quot;The range selected intersects another request&#39;s range. 請變更您的選擇。」

* If you still need to use the cell, right-click on the desired cell or cells, and select **[!UICONTROL Delete Request]**.

如果您想避免這項訊息，可以採用兩種方法：

* 藉由將格式新增至已具有請求和映射的儲存格，來規劃報表的格式
* 測試含映射之試算表的區域

若要測試含內嵌請求的區域，您可以：

* Launch the [!UICONTROL Request Manager] and click on individual requests listed in the table. 按一下請求會反白顯示已映射請求的試算表儲存格。
* Select cells in the spreadsheet you intend to use for a new mapping and click [!UICONTROL From Sheet]. The [!UICONTROL Request Manager] selects the request in the list which has an output item that intersects the selected cell. 如果它未選擇任何請求，表示可使用該儲存格。
* Select cells in the spreadsheet, right-click in the context menu and verify if [!UICONTROL Edit Request] is available. 如果可使用，表示請求與這些儲存格相關。
