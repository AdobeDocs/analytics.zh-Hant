---
description: 瞭解如何選取儲存格範圍、選取儲存格的技巧以及疑難排解對應問題。
title: 瞭解如何將度量和維度對映至儲存格
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
feature: Report Builder
role: User, Admin
exl-id: e63fc679-39eb-417b-9a2b-6620db63a824
TQID: https://experienceleague.adobe.com/yeU4gugMR2nSKwjo4LuX79spXIaD4UtuaTQ52bZwGrU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 676
ht-degree: 25%

---

# 將量度和維度對應至儲存格

{{legacy-arb}}

在開始將專案對應至試算表之前，請確定試算表未受到保護。 如果工作表的保護配置防止任何使用者動作，您將無法選取試算表中的儲存格。 首先，取消工作表保護，然後新增儲存格對應。

可對映的區域和儲存格數量會根據您選取的量度、粒度、日期範圍及您設定的篩選而有所不同。 例如，如果您選取[!UICONTROL 網站度量] > [!UICONTROL 流量報表]、設定[!UICONTROL 周]粒度，並設定[!UICONTROL 最近2週]的日期範圍，系統會在[!UICONTROL 請求精靈：步驟2]中提示您對映三個儲存格（使用[!UICONTROL 自訂配置]時）。 該請求會擷取第一週的資料及第二週的資料，其中每個資料點值等於頁面檢視的值。 您的第三個儲存格可作為列標題，使用[!UICONTROL 「格式選項」]進行設定。

如果您誤將不相容的位置對應到試算表上，Report Builder會發出錯誤。

如需詳細資訊，請參閱下列章節：

* [選擇儲存格範圍](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [選取儲存格的技巧](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [對映時發生的問題](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## 選取儲存格範圍 {#section_1E37FB46DA194FB7A1050B8833A48AC6}

在「[!UICONTROL 請求精靈: 步驟 2]」中，當您啟用趨勢化請求的「[!UICONTROL 自訂配置]」時，可以將請求映射至某個範圍內的儲存格。

按一下您要對應的專案旁的&#x200B;**[!UICONTROL 範圍選擇器]** ![select_cell_icon.png](assets/select_cell_icon.png)。

* **範圍內的所有儲存格：**&#x200B;要求您為[!UICONTROL 「自訂配置」]樣式的請求選擇一組儲存格。
* **範圍的第一個儲存格：**&#x200B;可讓您選擇範圍內左上角的儲存格，並顯示[!UICONTROL 「範圍」]方向以便指定水平或垂直方向的輸入和輸出儲存格 (欄或列)。 此選項可讓Report Builder為您選取儲存格。
* **範圍方向：**&#x200B;可讓您指定欄或列方向的儲存格範圍。
* **選擇範圍的上方儲存格位置：**&#x200B;顯示儲存格參考。

## 選擇儲存格的技巧 {#section_760421C3D7F84D67A639174710C93B22}

您可以按一下&#x200B;**[!UICONTROL 「選擇範圍」]**&#x200B;圖示 ![select_cell_icon.png](assets/select_cell_icon.png)

選擇資料，然後在試算表內按一下滑鼠，並拖曳到需要的儲存格範圍。 連續選取範圍會以黑色邊框框線。

![](assets/twenty_cells.gif)

個別選取的列在每一列周圍都有薄的白色邊框。

![](assets/twoXten_cells_highlighted.gif)

若要在一個要求中對應個別的列，請使用[!UICONTROL Control]鍵，然後按一下並將游標拖曳到所需的儲存格上。 如果您的請求需要四個區域，每個有10個儲存格，而不是一個連續區域，每個區域有40個儲存格，您就可以這麼做。

![](assets/map4.png)

選取儲存格後，再按一下[!UICONTROL 範圍選取]表單上的&#x200B;**[!UICONTROL 範圍選取器]**&#x200B;以返回[!UICONTROL 請求精靈：步驟2]。

## 疑難排解對應問題{#section_CC1BCF841291447EB3A994EB08F3A099}

如果您錯誤地選擇對映到已有作用中對應的儲存格，範圍選擇器圖示旁邊的文字方塊中就不會出現任何儲存格參照。 當您按一下[!UICONTROL 確定]時，Report Builder會顯示錯誤，*選取的範圍與另一個要求的範圍相交。 請變更您的選擇。*

* 如果您仍需要使用儲存格，請以滑鼠右鍵按一下想要的儲存格，然後選取&#x200B;**[!UICONTROL 刪除請求]**。

如果您想避免這項訊息，可以採用兩種方法：

* 將格式新增至具有請求和對映的儲存格，以計畫報表的格式
* 測試包含對應的試算表區域

若要測試含嵌入請求的區域，您可以：

* 啟動[!UICONTROL 請求管理員]，然後按一下表格中列出的個別請求。 按一下請求會醒目顯示請求所對應之試算表的儲存格。
* 在試算表中選取要用於新對應的儲存格，然後按一下[!UICONTROL 從工作表]。 [!UICONTROL 請求管理員]會選取清單中有與所選儲存格相交的輸出專案的請求。 如果未選取任何請求，則可使用儲存格。
* 選取試算表中的儲存格，在內容功能表中按一下滑鼠右鍵，然後確認[!UICONTROL 編輯請求]是否可用。 若是如此，則會有請求與這些儲存格相關聯。
