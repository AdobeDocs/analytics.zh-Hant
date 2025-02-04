---
description: 列設定依您拖放至表格中的元件而異。
title: 列設定
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
feature: Freeform Tables
role: User, Admin
exl-id: 9057e930-b4c6-439e-b82a-8ab9828de91d
source-git-commit: 6d6a7587fc4a41be1e7ad33d3ed0280b0d82d47c
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 14%

---


# 列設定


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [自由格式表格中的列與欄設定](https://video.tv.adobe.com/v/40382/?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

列設定會依您拖放至表格中的元件而異。若要存取表格列設定，請選取維度、篩選器、量度、時段旁的![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 設定]**，或每個物件內的劃分。

![自由格式表格醒目提示量度的「設定」圖示](assets/row-settings.png)

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 依位置劃分]** | 此設定預設為停用，且劃分會固定至靜態列項目。例如，想像您依「行銷管道」劃分前3個頁面維度專案（「首頁」、「搜尋結果」、「結帳」）。 接著，您離開專案，兩週後再回來。再次開啟專案時，前 3 個頁面已變更，現在「首頁」、「搜尋結果」和「結帳」是前 4 到 6 個頁面。您的「行銷管道」劃分預設仍會顯示在「首頁」、「搜尋結果」和「結帳」下方，即使它們現在位於第4到6列。 <br> 對比之下，**依位置劃分**&#x200B;總是會劃分前 3 個項目，無論前 3 個項目是什麼。請參考此範例，當您重新開啟專案時，行銷管道劃分會繫結至表格中的前3個頁面。 而非「首頁」、「搜尋結果」和「結帳」，它們現在位於第4-6列。 |
| **[!UICONTROL 百分比]** | **依欄**&#x200B;計算百分比（預設）：儲存格中顯示的百分比是根據欄位總計計算。 <br>**依列計算百分比**：儲存格中的百分比是跨列計算，而非將「總量」當作分母的整欄計算。 此計算方式對於趨勢百分比相當實用。 |
| **[!UICONTROL 欄總計]** | 這些設定僅適用於[靜態列](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。<br> **顯示為目前資料列的總和**&#x200B;會顯示資料表中資料列的使用者端總和，這表示總計&#x200B;*不會*&#x200B;刪除重複的量度，例如造訪次數或人員。<br> **顯示總計**&#x200B;會顯示伺服器端的加總，這表示去除重複專案的量度總數。 |

## 變更列計數

變更顯示的列數量:

1. 按一下表格第一欄頂端的&#x200B;**[!UICONTROL 列]**&#x200B;旁邊的數字。

   ![自由表格，顯示所顯示列數的下拉式清單。 已選取400列。](assets/change-row-count.gif)

1. 從下拉式清單中選取您希望表格顯示的列數量。


## 內容功能表

選取維度標題時，可使用下列內容功能表選項。

| 選項 | 說明 |
| --- | --- |
| **[!UICONTROL 將選取專案複製到剪貼簿]** | 將視覺效果中的選取範圍複製到剪貼簿。 |
| **[!UICONTROL 將專案下載為CSV檔（*維度名稱*）]** | 立即將視覺效果的維度專案（最多50,000個）下載到您的本機裝置。 所選維度最多50,000個維度專案。 |
| **[!UICONTROL 將選取專案下載為CSV]** | 立即將視覺效果的維度專案下載到您的本機裝置。 |
| **[!UICONTROL 為所有維度專案建立超連結]** | 為所有維度專案建立超連結。 檢視自由格式表格中維度的[超連結](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 編輯所有維度專案的超連結]** | 編輯所有維度專案的超連結。 檢視自由格式表格中維度的[超連結](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 移除所有維度專案的超連結]** | 移除所有維度專案的超連結。 檢視自由格式表格中維度的[超連結](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Delete]** | 從表格中刪除維度。 |
| **[!UICONTROL 視覺化]** | 使用任何可用的視覺效果來視覺化維度。 |
| **[!UICONTROL 僅顯示選取的列]** | 在視覺效果中僅顯示選取的專案。 |
| **[!UICONTROL 從選取專案建立附註]** | 開啟&#x200B;**[!UICONTROL 註解詳細資料]**&#x200B;以新增註解。 |


在自由表格中選取一或多個維度專案（第一欄）或一或多個個別儲存格時，可使用下列其他內容功能表選項。

| 選項 | 說明 |
| --- | --- |
| **[!UICONTROL 建立超連結]** | 建立專案的超連結。 檢視自由格式表格中維度的[超連結](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 編輯超連結]** | 編輯專案的超連結。 檢視自由格式表格中維度的[超連結](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 移除超連結]** | 移除專案的超連結。 檢視自由格式表格中維度的[超連結](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 劃分]** | 劃分維度專案。 從&#x200B;**[!UICONTROL Dimension]**、**[!UICONTROL 量度]**、**[!UICONTROL 篩選器]**&#x200B;或&#x200B;**[!UICONTROL 日期範圍]**&#x200B;的清單中選取。 使用&#x200B;*搜尋*&#x200B;替代搜尋元件。 |
| **[!UICONTROL 刪除選取的]** | 刪除選取的列（專案）。 |
| **[!UICONTROL 趨勢選取範圍]** | 為選取範圍建立趨勢線圖視覺效果。 |
| **[!UICONTROL 僅顯示選取的列]** | 在視覺效果中僅顯示選取的列。 |
| **[!UICONTROL 顯示所有列]** | 顯示視覺效果中的所有列。 |
| **[!UICONTROL 從選取專案建立篩選器]** | 開啟&#x200B;**[!UICONTROL 篩選器產生器]**，從選取專案建立篩選器。 |
| **[!UICONTROL 從選取專案建立對象]** | 開啟&#x200B;**[!UICONTROL 建立對象]**&#x200B;對話方塊以從選取專案建立對象。 |

選取量度欄標題時，可使用下列其他內容功能表選項。

| 選項 | 說明 |
|---|---|
| **[!UICONTROL 從選取專案建立量度]** | 從選取的量度建立新的量度。 量度可以是平均值、媒體、欄最大值、欄最小值、欄總和。 您也可以選取「在計算量度產生器中開啟」來建立計算量度。 |
| **[!UICONTROL 新增時段欄]** | 新增時段欄。 提供您幾個選項，其中面板的行事曆範圍會決定&#x200B;*日期範圍*： <li>**[!UICONTROL 在此日期範圍]**&#x200B;之前&#x200B;*的日期範圍*</li><li>**[!UICONTROL 這些&#x200B;*日期範圍*至此日期範圍]**。</li><li>**[!UICONTROL 自訂日期範圍至此日期範圍]**。 開啟&#x200B;**[!UICONTROL 日期範圍產生器]**&#x200B;以指定日期範圍。</li>如需詳細資訊，請參閱[日期比較](/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md)。 |
| **[!UICONTROL 比較時段]** | 新增比較時段欄。 僅當維度不是以時間為基準時可用。 提供您幾個決定&#x200B;*日期範圍*&#x200B;的選項： <li>**[!UICONTROL 在此日期範圍]**&#x200B;之前&#x200B;*的日期範圍*</li><li>**[!UICONTROL 自訂日期範圍至此日期範圍]**。 開啟&#x200B;**[!UICONTROL 日期範圍產生器]**&#x200B;以指定日期範圍。</li>如需詳細資訊，請參閱[日期比較](/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md)。 |
| **[!UICONTROL 修改歸因模型]** | 修改欄的歸因模型。 |
| **[!UICONTROL 比較歸因模型]** | 指定新的歸因模型，並將其與所選欄的歸因模型比較。 會新增一個欄，其中包含新的歸因模型量度。 此外，也會新增「百分比變更」欄以進行比較。 |
| **[!UICONTROL 重設資料行寬度]** | 將欄寬重設為預設寬度。 |
| **[!UICONTROL 從選取專案建立附註]** | 開啟&#x200B;**[!UICONTROL 註解詳細資料]**&#x200B;以新增註解。 |
| **[!UICONTROL 從選取專案建立篩選器]** | 開啟&#x200B;**[!UICONTROL 篩選器產生器]**，從選取專案建立篩選器。 |
| **[!UICONTROL 從選取專案建立對象]** | 開啟&#x200B;**[!UICONTROL 建立對象]**&#x200B;對話方塊以從選取專案建立對象。 |
