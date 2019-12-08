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

可映射的區域和儲存格數量會隨著選擇的度量、詳細程度、日期範圍及設定的篩選而改變。例如，如果您選擇「[!UICONTROL 網站度量]」&gt;「[!UICONTROL 流量報表]」、設定「[!UICONTROL 週]」詳細程度，然後設定「[!UICONTROL 最近 2 週]」的日期範圍，在「[!UICONTROL 請求精靈: 步驟 2]」中，系統會提示您映射三個儲存格 (若目前使用「[!UICONTROL 自訂配置]」)。請求會擷取第一週的資料和第二週的資料，而每個資料點值 = 頁面檢視的值。您的第三個儲存格可做為列標題 (使用「[!UICONTROL 格式選項]」進行設定)。

當您意外映射試算表中不相容的位置時，Report Builder 會發出錯誤。

以下章節包含更多資訊: 

* [選擇儲存格範圍](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [選擇儲存格的技巧](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [映射時發生的問題](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## 選擇儲存格範圍 {#section_1E37FB46DA194FB7A1050B8833A48AC6}

在「[!UICONTROL 請求精靈: 步驟 2]」中，當您啟用趨勢化請求的「[!UICONTROL 自訂配置]」時，可以將請求映射至某個範圍內的儲存格。

按一下「 **[!UICONTROL 範圍選]** 取 ![器」select_cell_icon.png](assets/select_cell_icon.png)

在您要對應的項目旁。

* **範圍內的所有儲存格:** 要求您為[!UICONTROL 「自訂配置」]樣式的請求選擇一組儲存格。
* **範圍的第一個儲存格:**&#x200B;可讓您選擇範圍內左上角的儲存格，並顯示[!UICONTROL 「範圍」]方向以便指定水平或垂直方向的輸入和輸出儲存格 (欄或列)。此選項可讓 Report Builder 為您選擇儲存格。
* **範圍方向:**&#x200B;可讓您指定欄或列方向的儲存格範圍。
* **選擇範圍的上方儲存格位置:** 顯示儲存格參考。

## Techniques for selecting cells {#section_760421C3D7F84D67A639174710C93B22}

You select the data by clicking the **[!UICONTROL Range Selection]** icon  ![select_cell_icon.png](assets/select_cell_icon.png)

 來選擇資料，然後在試算表內按一下滑鼠按 並拖曳到需要的儲存格範圍。此時，黑色邊框會勾勒出連續的選擇範圍。

![](assets/twenty_cells.gif)

個別選擇的列在每個列的周圍會有白色的細邊框。

![](assets/twoXten_cells_highlighted.gif)

若要映射一個請求中個別的列，請按住 [!UICONTROL Control] 鍵，然後按一下滑鼠按鍵並將游標拖曳至需要的儲存格。如果請求需要四個各有十個儲存格的區域 (而不是一個含有 40 個儲存格的連續區域)，您便可以使用這項操作。

![](assets/map4.png)

選擇儲存格後，再按一下「[!UICONTROL **選擇範圍]」表單中的「**[!UICONTROL 範圍選取器]」可返回「[!UICONTROL 請求精靈: 步驟 2]」。

## Issues when mapping {#section_CC1BCF841291447EB3A994EB08F3A099}

如果意外選擇映射至已有作用中映射的儲存格，您會發現範圍選取器圖示旁的文字方塊內不會出現儲存格參考。按一下「[!UICONTROL 確定]」時，Report Builder 會顯示錯誤「選擇的範圍與其他請求的範圍相交。請變更您的選擇。」

* If you still need to use the cell, right-click on the desired cell or cells, and select **[!UICONTROL Delete Request]**.

如果您想要避免這項訊息，可以採用兩種方法:

* 藉由將格式新增至已具有請求和映射的儲存格，來規劃報表的格式
* 測試含映射之試算表的區域

若要測試含內嵌請求的區域，您可以: 

* 啟動[!UICONTROL 「請求管理員」]並分別按一下表格中列示的個別請求。按一下請求會反白顯示已映射請求的試算表儲存格。
* 在試算表中選擇要用於新映射的儲存格，然後按一下[!UICONTROL 「從工作表」]。「[!UICONTROL 請求管理員]」會在清單中選擇含有與選定儲存格相交之輸出項目的請求。如果它未選擇任何請求，表示可使用該儲存格。
* 在試算表中選擇儲存格，接著在內容功能表中按一下滑鼠右鍵並確認是否可使用[!UICONTROL 「編輯請求」]。如果可使用，表示請求與這些儲存格相關。
